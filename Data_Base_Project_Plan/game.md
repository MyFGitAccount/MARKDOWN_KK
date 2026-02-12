# PROJECT: Esports Tournament & Player Statistics Database

## TRANSFORMING SPEEDRUN TO ESPORTS

**Esports Tournament Organization Database** - it has:

✅ **Real-life organization** (Esports organizations exist as formal companies)
✅ **Business context** (Sponsorships, prize money, team management)
✅ **Real examples** (Hong Kong Esports Association, Cyber Games Arena, Talon Esports)
✅ **Complex business rules** (Contracts, tournament brackets, prize distribution)
✅ **Input forms available** (Tournament registration forms, player contracts, sponsor agreements)

---

# ESPORTS TOURNAMENT & PLAYER MANAGEMENT SYSTEM

## SUITABILITY ASSESSMENT: ⭐⭐⭐⭐ (4/5)

**Why This Works:**
- **Real organizations**: Hong Kong Esports Association (HKESA), Cyber Games Arena (CGA), Talon Esports, PSG Talon
- **Real input forms**: Tournament registration forms, player contract templates, sponsor proposal forms, team roster submission forms
- **Business context**: Prize money tracking, sponsor ROI, player salaries, tournament revenue
- **Complex data relationships**: Many-to-many (players to teams), hierarchical (tournaments to matches), temporal (contract validity periods)
- **Reporting needs**: Tournament brackets, player performance analytics, financial reports

---

## 1. DATABASE SCHEMA OVERVIEW

### Complete Table Structure with Sample Data

| **Table Name** | **Field Name** | **Data Type** | **Constraints** | **Description** | **Sample Data** |
|----------------|----------------|---------------|-----------------|-----------------|-----------------|
| **Organizations** | org_id | INTEGER | PRIMARY KEY AUTOINCREMENT | Unique ID | 1001 |
| | org_name | TEXT | UNIQUE NOT NULL | Organization name | Cyber Games Arena |
| | org_type | TEXT | NOT NULL | Tournament Org/Team Org/Sponsor | Tournament Organizer |
| | registration_number | TEXT | UNIQUE | Business registration | 65432178-000 |
| | established_date | DATE | | Founded date | 2015-06-01 |
| | headquarters | TEXT | | City, Country | Hong Kong |
| | website | TEXT | | Official website | www.cybergamesarena.hk |
| | contact_person | TEXT | | Primary contact | Wong Ka Chun |
| | contact_email | TEXT | | Email | info@cga.hk |
| | contact_phone | TEXT | | Phone | 28901234 |
| | verification_status | TEXT | DEFAULT 'Pending' | Verified/Unverified | Verified |

| **Table Name** | **Field Name** | **Data Type** | **Constraints** | **Description** | **Sample Data** |
|----------------|----------------|---------------|-----------------|-----------------|-----------------|
| **Teams** | team_id | INTEGER | PRIMARY KEY AUTOINCREMENT | Unique ID | 501 |
| | team_name | TEXT | UNIQUE NOT NULL | Official team name | PSG Talon |
| | short_name | TEXT | | Abbreviation | PSGT |
| | logo_url | TEXT | | Team logo path | /logos/psgtalon.png |
| | region | TEXT | NOT NULL | HK/TW/KR/CN/Global | Hong Kong |
| | org_id | INTEGER | FOREIGN KEY REFERENCES Organizations | Parent organization | 1005 |
| | established_date | DATE | | Team founded | 2020-01-15 |
| | disbanded_date | DATE | | If disbanded | NULL |
| | team_house_address | TEXT | | Training facility | Unit B, 22/F, K11, TST |
| | total_earnings | DECIMAL(12,2) | DEFAULT 0 | Cumulative prize money | 2500000.00 |
| | world_ranking | INTEGER | | Current global rank | 12 |
| | social_media_handle | TEXT | | Instagram/Twitter | @psgtalon |

| **Table Name** | **Field Name** | **Data Type** | **Constraints** | **Description** | **Sample Data** |
|----------------|----------------|---------------|-----------------|-----------------|-----------------|
| **Players** | player_id | INTEGER | PRIMARY KEY AUTOINCREMENT | Unique ID | 10001 |
| | gamer_tag | TEXT | UNIQUE NOT NULL | In-game name | Maple |
| | full_name | TEXT | NOT NULL | Legal name | Wong Kam Hung |
| | hkid | TEXT | UNIQUE | HK ID (for local players) | Y3456789 |
| | nationality | TEXT | NOT NULL | Country of origin | Hong Kong |
| | date_of_birth | DATE | NOT NULL | Birth date | 2000-10-05 |
| | age | INTEGER | Computed | Calculated age | 25 |
| | gender | TEXT | | M/F/Other | M |
| | primary_game | TEXT | NOT NULL | Main esports title | League of Legends |
| | role_position | TEXT | | Mid Laner/Support/etc. | Mid Laner |
| | join_date | DATE | | Professional debut | 2018-03-20 |
| | status | TEXT | DEFAULT 'Active' | Active/Inactive/Retired | Active |
| | current_team_id | INTEGER | FOREIGN KEY REFERENCES Teams | Current team | 501 |
| | contract_start_date | DATE | | Current contract start | 2024-01-01 |
| | contract_end_date | DATE | | Current contract end | 2025-12-31 |
| | monthly_salary | DECIMAL(10,2) | | HKD | 45000.00 |
| | total_earnings | DECIMAL(12,2) | DEFAULT 0 | Prize money won | 850000.00 |
| | social_media_followers | INTEGER | | Across platforms | 125000 |
| | email | TEXT | | Contact | maple@psgtalon.gg |
| | phone | TEXT | | Contact | 98765432 |

| **Table Name** | **Field Name** | **Data Type** | **Constraints** | **Description** | **Sample Data** |
|----------------|----------------|---------------|-----------------|-----------------|-----------------|
| **Tournaments** | tournament_id | INTEGER | PRIMARY KEY AUTOINCREMENT | Unique ID | 2001 |
| | tournament_name | TEXT | NOT NULL | Official name | CGA Hong Kong Esports Festival 2025 |
| | game_title | TEXT | NOT NULL | Game played | League of Legends |
| | organizer_id | INTEGER | FOREIGN KEY REFERENCES Organizations | Tournament organizer | 1001 |
| | tournament_level | TEXT | | Local/Regional/International | Regional |
| | format_type | TEXT | | Single elim/Double elim/Group+KO | Double Elimination |
| | venue | TEXT | | Physical location | HKCEC, Wan Chai |
| | online_or_offline | TEXT | | Online/Offline/Hybrid | Offline |
| | start_date | DATE | NOT NULL | Tournament start | 2025-07-15 |
| | end_date | DATE | NOT NULL | Tournament end | 2025-07-20 |
| | registration_start | DATE | | Team registration opens | 2025-04-01 |
| | registration_end | DATE | | Team registration closes | 2025-06-15 |
| | max_teams | INTEGER | | Participant limit | 16 |
| | registered_teams | INTEGER | DEFAULT 0 | Current count | 16 |
| | prize_pool_total | DECIMAL(10,2) | NOT NULL | Total prize money | 500000.00 |
| | entry_fee | DECIMAL(10,2) | | Per team fee | 2000.00 |
| | status | TEXT | | Upcoming/Ongoing/Completed | Upcoming |
| | stream_url | TEXT | | Twitch/Youtube | www.twitch.tv/cga |
| | rules_document | TEXT | | PDF path | /rules/CGA2025.pdf |

| **Table Name** | **Field Name** | **Data Type** | **Constraints** | **Description** | **Sample Data** |
|----------------|----------------|---------------|-----------------|-----------------|-----------------|
| **Tournament_Registrations** | registration_id | INTEGER | PRIMARY KEY AUTOINCREMENT | Unique ID | 30001 |
| | tournament_id | INTEGER | FOREIGN KEY REFERENCES Tournaments | Tournament | 2001 |
| | team_id | INTEGER | FOREIGN KEY REFERENCES Teams | Team | 501 |
| | registration_date | TIMESTAMP | NOT NULL | When registered | 2025-06-10 14:30:00 |
| | payment_status | TEXT | | Paid/Pending/Refunded | Paid |
| | payment_amount | DECIMAL(10,2) | | Entry fee paid | 2000.00 |
| | payment_date | DATE | | Date paid | 2025-06-11 |
| | roster_submitted | BOOLEAN | DEFAULT 0 | Team roster uploaded | 1 |
| | roster_verified | BOOLEAN | DEFAULT 0 | Verified by organizer | 1 |
| | seed_ranking | INTEGER | | Tournament seed | 1 |
| | status | TEXT | | Registered/Checked-in/Disqualified | Registered |

| **Table Name** | **Field Name** | **Data Type** | **Constraints** | **Description** | **Sample Data** |
|----------------|----------------|---------------|-----------------|-----------------|-----------------|
| **Matches** | match_id | INTEGER | PRIMARY KEY AUTOINCREMENT | Unique ID | 50001 |
| | tournament_id | INTEGER | FOREIGN KEY REFERENCES Tournaments | Tournament | 2001 |
| | match_number | TEXT | | e.g., WB Round 1, LB Final | Grand Final |
| | team1_id | INTEGER | FOREIGN KEY REFERENCES Teams | First team | 501 |
| | team2_id | INTEGER | FOREIGN KEY REFERENCES Teams | Second team | 505 |
| | winner_id | INTEGER | FOREIGN KEY REFERENCES Teams | Winning team | 501 |
| | loser_id | INTEGER | FOREIGN KEY REFERENCES Teams | Losing team | 505 |
| | team1_score | INTEGER | | Games won by team1 | 3 |
| | team2_score | INTEGER | | Games won by team2 | 1 |
| | match_date | TIMESTAMP | | Scheduled datetime | 2025-07-18 19:00:00 |
| | duration_minutes | INTEGER | | Match length | 125 |
| | stage | TEXT | | Group Stage/Quarterfinal/Semifinal/ Final | Grand Final |
| | bracket_position | TEXT | | Upper/Lower bracket | Upper Final |
| | vod_url | TEXT | | Video on demand | /vod/cga2025/gf1 |
| | referee_id | INTEGER | FOREIGN KEY REFERENCES Staff | Match official | 8005 |
| | status | TEXT | | Scheduled/Ongoing/Completed | Completed |

| **Table Name** | **Field Name** | **Data Type** | **Constraints** | **Description** | **Sample Data** |
|----------------|----------------|---------------|-----------------|-----------------|-----------------|
| **Games** | game_id | INTEGER | PRIMARY KEY AUTOINCREMENT | Unique ID | 60001 |
| | match_id | INTEGER | FOREIGN KEY REFERENCES Matches | Parent match | 50001 |
| | game_number | INTEGER | | Game 1/2/3/4/5 | 1 |
| | duration_seconds | INTEGER | | Game length | 2475 |
| | winning_team_id | INTEGER | FOREIGN KEY REFERENCES Teams | Winner of game | 501 |
| | losing_team_id | INTEGER | FOREIGN KEY REFERENCES Teams | Loser of game | 505 |
| | first_blood_team_id | INTEGER | | First kill team | 501 |
| | first_tower_team_id | INTEGER | | First tower team | 501 |
| | first_baron_team_id | INTEGER | | First Baron Nashor | 505 |
| | team1_kills | INTEGER | | Team 1 kill count | 18 |
| | team2_kills | INTEGER | | Team 2 kill count | 9 |
| | team1_gold | INTEGER | | Team 1 gold earned | 65400 |
| | team2_gold | INTEGER | | Team 2 gold earned | 52300 |
| | mvp_player_id | INTEGER | FOREIGN KEY REFERENCES Players | Player of the game | 10001 |
| | vod_timestamp | TEXT | | Start time in VOD | 01:23:45 |

| **Table Name** | **Field Name** | **Data Type** | **Constraints** | **Description** | **Sample Data** |
|----------------|----------------|---------------|-----------------|-----------------|-----------------|
| **Player_Performance** | performance_id | INTEGER | PRIMARY KEY AUTOINCREMENT | Unique ID | 700001 |
| | game_id | INTEGER | FOREIGN KEY REFERENCES Games | Specific game | 60001 |
| | player_id | INTEGER | FOREIGN KEY REFERENCES Players | Player | 10001 |
| | team_id | INTEGER | FOREIGN KEY REFERENCES Teams | Player's team | 501 |
| | champion_character | TEXT | NOT NULL | Character played | Azir |
| | kills | INTEGER | | Number of kills | 5 |
| | deaths | INTEGER | | Number of deaths | 1 |
| | assists | INTEGER | | Number of assists | 8 |
| | kda_ratio | DECIMAL(5,2) | Computed | (K+A)/D | 13.00 |
| | creep_score | INTEGER | | Minions killed | 345 |
| | gold_earned | INTEGER | | Gold earned | 16200 |
| | damage_dealt | INTEGER | | Total damage | 45600 |
| | vision_score | INTEGER | | Wards placed/killed | 42 |
| | mvp_points | INTEGER | | Performance rating | 9.5 |
| | time_played_seconds | INTEGER | | Time in game | 2475 |

| **Table Name** | **Field Name** | **Data Type** | **Constraints** | **Description** | **Sample Data** |
|----------------|----------------|---------------|-----------------|-----------------|-----------------|
| **Prize_Distribution** | prize_id | INTEGER | PRIMARY KEY AUTOINCREMENT | Unique ID | 40001 |
| | tournament_id | INTEGER | FOREIGN KEY REFERENCES Tournaments | Tournament | 2001 |
| | rank_position | INTEGER | NOT NULL | 1st, 2nd, 3rd, etc. | 1 |
| | team_id | INTEGER | FOREIGN KEY REFERENCES Teams | Winning team | 501 |
| | prize_amount | DECIMAL(10,2) | NOT NULL | Money awarded | 250000.00 |
| | trophy_awarded | TEXT | | Physical award | Gold Trophy |
| | medal_type | TEXT | | Gold/Silver/Bronze | Gold |
| | distribution_date | DATE | | When paid | 2025-07-25 |
| | payment_status | TEXT | | Paid/Pending | Paid |

| **Table Name** | **Field Name** | **Data Type** | **Constraints** | **Description** | **Sample Data** |
|----------------|----------------|---------------|-----------------|-----------------|-----------------|
| **Sponsors** | sponsor_id | INTEGER | PRIMARY KEY AUTOINCREMENT | Unique ID | 3001 |
| | org_id | INTEGER | FOREIGN KEY REFERENCES Organizations | Sponsor organization | 1010 |
| | sponsor_name | TEXT | NOT NULL | Brand name | Logitech |
| | industry | TEXT | | Gaming/Hardware/Energy Drink | Hardware |
| | contact_person | TEXT | | Account manager | Sarah Lee |
| | contact_email | TEXT | | Email | slee@logitech.com |
| | contact_phone | TEXT | | Phone | 23456789 |

| **Table Name** | **Field Name** | **Data Type** | **Constraints** | **Description** | **Sample Data** |
|----------------|----------------|---------------|-----------------|-----------------|-----------------|
| **Sponsorship_Deals** | deal_id | INTEGER | PRIMARY KEY AUTOINCREMENT | Unique ID | 35001 |
| | sponsor_id | INTEGER | FOREIGN KEY REFERENCES Sponsors | Sponsor | 3001 |
| | sponsored_entity_type | TEXT | | Tournament/Team/Player | Tournament |
| | tournament_id | INTEGER | FOREIGN KEY REFERENCES Tournaments | If tournament | 2001 |
| | team_id | INTEGER | FOREIGN KEY REFERENCES Teams | If team | NULL |
| | player_id | INTEGER | FOREIGN KEY REFERENCES Players | If player | NULL |
| | deal_value | DECIMAL(12,2) | NOT NULL | Contract value | 500000.00 |
| | start_date | DATE | NOT NULL | Deal start | 2025-01-01 |
| | end_date | DATE | NOT NULL | Deal end | 2025-12-31 |
| | sponsorship_type | TEXT | | Title/Presenting/Premium/Standard | Title Sponsor |
| | benefits_provided | TEXT | | Cash/Equipment/Service | Cash + Equipment |
| | exclusivity | BOOLEAN | | Exclusive category? | 1 |
| | activation_requirements | TEXT | | Logo placement, mentions | Main stage banner |
| | status | TEXT | | Active/Completed/Terminated | Active |

| **Table Name** | **Field Name** | **Data Type** | **Constraints** | **Description** | **Sample Data** |
|----------------|----------------|---------------|-----------------|-----------------|-----------------|
| **Staff** | staff_id | INTEGER | PRIMARY KEY AUTOINCREMENT | Unique ID | 8001 |
| | org_id | INTEGER | FOREIGN KEY REFERENCES Organizations | Employer | 1001 |
| | full_name | TEXT | NOT NULL | Staff name | Chan Wai Man |
| | role | TEXT | NOT NULL | Referee/Admin/Commentator | Head Referee |
| | qualification | TEXT | | Certifications | Level 2 Esports Referee |
| | hire_date | DATE | | Employment start | 2023-04-01 |
| | email | TEXT | | Work email | wmchan@cga.hk |
| | phone | TEXT | | Contact | 91237890 |

| **Table Name** | **Field Name** | **Data Type** | **Constraints** | **Description** | **Sample Data** |
|----------------|----------------|---------------|-----------------|-----------------|-----------------|
| **Transfer_History** | transfer_id | INTEGER | PRIMARY KEY AUTOINCREMENT | Unique ID | 90001 |
| | player_id | INTEGER | FOREIGN KEY REFERENCES Players | Player | 10001 |
| | from_team_id | INTEGER | FOREIGN KEY REFERENCES Teams | Previous team | 503 |
| | to_team_id | INTEGER | FOREIGN KEY REFERENCES Teams | New team | 501 |
| | transfer_date | DATE | NOT NULL | Date of move | 2024-01-01 |
| | transfer_fee | DECIMAL(12,2) | | Buyout amount | 350000.00 |
| | contract_length_months | INTEGER | | Duration | 24 |
| | transfer_type | TEXT | | Free agent/Transfer/Loan | Transfer |
| | approved_by | INTEGER | FOREIGN KEY REFERENCES Staff | League official | 8002 |

---

## 2. USER REQUIREMENTS

### A. Functional Requirements

#### Tournament Organizer Requirements:
1. **Tournament Management**: Create, update, and manage tournament schedules
2. **Registration Processing**: Accept team registrations and verify eligibility
3. **Bracket Generation**: Automatically generate tournament brackets based on format
4. **Match Scheduling**: Schedule matches and assign referees
5. **Result Entry**: Record match scores and update brackets in real-time
6. **Prize Distribution**: Calculate and process prize payments to teams
7. **Sponsorship Tracking**: Manage sponsor deals and activation requirements
8. **Participant Communication**: Send notifications to teams about schedules
9. **Stream Integration**: Link VODs and stream URLs to matches
10. **Report Generation**: Generate tournament summary reports with viewership and engagement stats

#### Team Manager Requirements:
1. **Team Registration**: Register team for tournaments
2. **Roster Management**: Submit and verify tournament rosters
3. **Player Contracts**: Track player contract periods and salaries
4. **Performance Analytics**: View team and individual player statistics
5. **Financial Tracking**: Monitor prize earnings and sponsorship income
6. **Transfer Management**: Process player transfers and contract renewals

#### Player Requirements:
1. **Profile Management**: Maintain personal and contact information
2. **Performance Dashboard**: View personal statistics across all tournaments
3. **Career History**: Access match history and achievements
4. **Earnings Tracking**: View prize money earned and payment status
5. **Contract Information**: View current contract terms and expiration

#### Sponsor Requirements:
1. **ROI Tracking**: View impressions and brand visibility across tournaments
2. **Deal Management**: Track sponsorship contract status and renewal dates
3. **Performance Reports**: Access engagement metrics for sponsored events/teams
4. **Invoice Management**: View sponsorship payment history

#### Fan/Public Requirements (Read-only):
1. **Tournament Information**: View tournament schedules and results
2. **Leaderboards**: Access player and team rankings
3. **Match History**: Browse past matches and VODs
4. **Statistics**: View aggregated performance statistics

### B. Non-Functional Requirements

1. **Real-time Updates**: Match results should update brackets within 1 minute
2. **Accuracy**: Prize money calculations must be 100% accurate
3. **Historical Data Preservation**: All match data becomes permanent after tournament ends
4. **Concurrency**: Support 10,000+ concurrent viewers during tournament finals
5. **Data Integrity**: No orphaned player performance records
6. **Financial Audit Trail**: All prize distributions must be fully auditable
7. **Mobile Responsiveness**: Basic functionality on mobile devices for team managers
8. **Multi-language Support**: English and Traditional Chinese interfaces

---

## 3. DATABASE DESIGN DOCUMENT

### Entity-Relationship Model Description

```
Organizations (1) -----< (M) Teams
      |                     |
      |                     +----< (M) Players
      |                     |
      +----< (M) Tournaments
      |        |      |
      |        |      +----< (M) Matches
      |        |      |        |
      |        |      |        +----< (M) Games
      |        |      |                 |
      |        |      |                 +----< (M) Player_Performance
      |        |      |
      |        |      +----< (M) Prize_Distribution
      |        |
      |        +----< (M) Tournament_Registrations >----- (M) Teams
      |
      +----< (M) Staff

Teams (1) -----< (M) Players
  |              |
  |              +----< (M) Transfer_History
  |
  +----< (M) Tournament_Registrations >----- (M) Tournaments
  |
  +----< (M) Matches (as team1/team2)
  |
  +----< (M) Prize_Distribution

Sponsors (1) -----< (M) Sponsorship_Deals
                       |
                       +--- (0/1) Tournaments
                       +--- (0/1) Teams
                       +--- (0/1) Players
```

### Business Rules

1. **Player Eligibility**: 
   - Player must be at least 16 years old to compete in professional tournaments
   - Player can only be under contract with one team at a time
   - Player cannot play against their contracted team in a tournament

2. **Team Registration**:
   - Team must have minimum 5 players and maximum 7 players registered for tournament
   - Team cannot register for tournament after registration deadline
   - Team must have valid organization backing for Tier 1 tournaments

3. **Tournament Operations**:
   - Match cannot have winner without at least one game completed
   - Tournament cannot end before all scheduled matches are completed
   - Prize money must be distributed within 30 days of tournament completion

4. **Financial Rules**:
   - Sponsor deals cannot overlap exclusivity for same category
   - Player transfer fees must be recorded for professional league compliance
   - Tournament prize pool must equal sum of all prize distribution amounts

5. **Data Integrity**:
   - Player performance stats must sum to match totals (e.g., team kills = sum of player kills)
   - Match winner must equal team with higher game score
   - Team cannot be registered for two matches at same time in same tournament

### Complex Queries to Implement

1. **Player Career Statistics with Moving Averages**
```sql
-- Calculate player's KDA trend over last 10 games
WITH recent_games AS (
    SELECT 
        pp.player_id,
        pp.game_id,
        pp.kills,
        pp.deaths,
        pp.assists,
        m.match_date,
        ROW_NUMBER() OVER (PARTITION BY pp.player_id ORDER BY m.match_date DESC) as game_rank
    FROM Player_Performance pp
    JOIN Games g ON pp.game_id = g.game_id
    JOIN Matches m ON g.match_id = m.match_id
    WHERE pp.player_id = 10001
    AND m.status = 'Completed'
)
SELECT 
    AVG((kills + assists) / NULLIF(deaths, 0)) as avg_kda_last_10,
    SUM(kills) as total_kills,
    SUM(assists) as total_assists,
    AVG(creep_score) as avg_cs
FROM recent_games
WHERE game_rank <= 10;
```

2. **Tournament ROI for Sponsors**
```sql
SELECT 
    s.sponsor_name,
    t.tournament_name,
    sd.deal_value,
    COUNT(DISTINCT v.viewer_id) as estimated_viewers,
    COUNT(DISTINCT m.match_id) * 2 as broadcast_hours,
    ROUND(sd.deal_value / COUNT(DISTINCT v.viewer_id), 2) as cost_per_viewer
FROM Sponsorship_Deals sd
JOIN Sponsors s ON sd.sponsor_id = s.sponsor_id
JOIN Tournaments t ON sd.tournament_id = t.tournament_id
JOIN Matches m ON t.tournament_id = m.tournament_id
LEFT JOIN Viewership_Log v ON m.match_id = v.match_id
WHERE sd.tournament_id = 2001
GROUP BY s.sponsor_id;
```

3. **Team Transfer Market Activity**
```sql
SELECT 
    t.team_name,
    COUNT(th.transfer_id) as transfers_in,
    SUM(th.transfer_fee) as total_spent,
    AVG(th.transfer_fee) as avg_transfer_fee
FROM Teams t
JOIN Transfer_History th ON t.team_id = th.to_team_id
WHERE th.transfer_date >= DATE('now', '-1 year')
GROUP BY t.team_id
ORDER BY total_spent DESC;
```

---

## 4. IMPLEMENTATION NOTES

### Real Organizations to Base Your Project On

| **Organization** | **Type** | **Location** | **Potential Input Forms** |
|-----------------|---------|-------------|-------------------------|
| **Cyber Games Arena (CGA)** | Tournament Organizer | Hong Kong | Tournament registration forms, match result sheets |
| **Hong Kong Esports Association (HKESA)** | Governing Body | Hong Kong | Player registration forms, team certification forms |
| **Talon Esports** | Professional Team | Hong Kong | Player contracts, sponsorship proposals |
| **PSG Talon** | Professional Team | Hong Kong | Roster submission forms, transfer documents |
| **Logitech G** | Sponsor | Global | Sponsorship agreement templates |
| **CGA Hong Kong Esports Festival** | Annual Event | Hong Kong | Event schedule, bracket templates |

### Sample Input Form References

Collect these real forms from the above organizations:

1. **Tournament Registration Form** - Team information, roster, payment
2. **Player Contract Template** - Salary, duration, termination clauses
3. **Match Score Sheet** - Official match result documentation
4. **Sponsorship Proposal Form** - Benefits, costs, exclusivity
5. **Transfer Declaration Form** - Player transfer between teams
6. **Tournament Schedule Template** - Match timing and assignments

### Suggested Project Timeline

| **Week** | **Tasks** |
|----------|----------|
| 1-2 | Research Hong Kong esports organizations; collect real forms from CGA/HKESA websites |
| 3-4 | Create ER diagram; map all fields from real forms to database tables |
| 5-6 | Implement SQLite database with all 15+ tables and relationships |
| 7-8 | Populate with realistic sample data (6 teams, 30 players, 2 tournaments, 20 matches) |
| 9-10 | Implement complex queries for player stats, team rankings, sponsor ROI |
| 11-12 | Create transcript-style tournament reports and presentation slides |
| 13 | Final testing and submission |

### Sample Data Requirements

| **Entity** | **Minimum Records** | **Notes** |
|-----------|---------------------|---------|
| Organizations | 5 | 2 tournament orgs, 2 teams, 1 sponsor |
| Teams | 6 | Mix of HK and international teams |
| Players | 30 | 5 players per team minimum |
| Tournaments | 2 | One completed, one upcoming |
| Matches | 20 | At least full bracket for one tournament |
| Games | 60 | 3 games per match average |
| Player Performance | 300 | Records for each player in each game |
| Sponsorship Deals | 4 | Various sponsor-entity combinations |

---

## 5. ADVANTAGES OVER PURE SPEEDRUN DATABASE

| **Aspect** | **Pure Speedrun** | **Esports Tournament (This Design)** |
|-----------|-------------------|-------------------------------------|
| **Real Organization** | ❌ Community-run sites | ✅ HKESA, CGA, Talon Esports |
| **Business Context** | ❌ Hobbyist | ✅ Sponsorships, salaries, prize money |
| **Financial Tracking** | ❌ None | ✅ Contracts, transfers, ROI |
| **Complex Relationships** | ❌ Player-Game only | ✅ Tournaments-Matches-Games-Performance |
| **Input Forms Available** | ❌ Difficult | ✅ Registration, contracts, score sheets |
| **Academic Relevance** | ⚠️ Limited | ✅ Information system for real business |
| **Career Relevance** | ❌ Niche | ✅ Sports analytics, event management |

---

## 6. DELIVERABLES CHECKLIST

| **Deliverable** | **Status** | **Notes** |
|-----------------|-----------|---------|
| Real organization input forms (scanned/photos) | ✅ | From CGA/HKESA websites |
| ER Diagram with all entities and relationships | ✅ | 15+ tables |
| SQLite database creation script | ✅ | With all constraints |
| Sample data population script | ✅ | 6 teams, 30 players, 2 tournaments |
| Player statistics view | ✅ | KDA, win rates, earnings |
| Tournament bracket progression query | ✅ | Recursive CTE for bracket path |
| Sponsor ROI calculation | ✅ | Cost per impression/viewer |
| Team financial summary | ✅ | Prize money + sponsorship - salaries |
| Transfer market activity report | ✅ | Recent transfers with fees |
| Presentation slides | ✅ | 20-25 slides with screenshots |
| Project report | ✅ | 1500-2000 words |

---

## FINAL VERDICT

**This Esports Tournament Database is now HIGHLY SUITABLE (4/5)** for your academic project because:

✅ **Real organizations exist in Hong Kong** - you can literally visit Cyber Games Arena's website and download tournament registration forms

✅ **Rich business context** - sponsorships, player salaries, transfer fees, prize money - all real business transactions

✅ **Complex but understandable** - the domain is familiar to young people but the data model is sophisticated enough for a university project

✅ **Multiple user types** - organizers, teams, players, sponsors, fans - each with different access patterns

✅ **Reporting needs** - tournament summaries, player analytics, financial reports

✅ **Scalable design** - can start simple (tournaments + teams + matches) and add complexity

✅ **Easy to find input forms** - all Hong Kong esports organizations have public registration forms

**Recommended approach**: Contact Cyber Games Arena (info@cybergamesarena.hk) and explain you're a university student doing a database project on esports tournament management. Ask if they can share blank versions of their:
- Tournament registration form
- Match score sheet
- Team roster submission form

