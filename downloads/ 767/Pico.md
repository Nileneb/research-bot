<?xml version="1.0" encoding="UTF-8" standalone="yes"?>
<output>
  <topic>Effects of Gamification on Leadership Skills Development in Older Adults</topic>
  <pico>
    <population>
      <label>Older adults</label>
      <mesh>Aged</mesh>
      <mesh>Aged, 80 and over</mesh>
      <text_words>older adults</text_words>
      <text_words>elderly</text_words>
      <text_words>seniors</text_words>
    </population>
    <intervention_exposure>
      <label>Gamification</label>
      <mesh>Gamification</mesh>
      <text_words>gamification</text_words>
      <text_words>gamif*</text_words>
      <text_words>game-based learning</text_words>
      <text_words>gamified training</text_words>
    </intervention_exposure>
    <comparison/>
    <outcome>
      <label>Leadership skills development</label>
      <mesh>Leadership</mesh>
      <text_words>leadership development</text_words>
      <text_words>leadership training</text_words>
      <text_words>leadership competency</text_words>
      <text_words>leader* skill*</text_words>
    </outcome>
  </pico>
  <exclusions>
    <non_human>true</non_human>
    <terms>animal</terms>
    <terms>rats</terms>
    <terms>mice</terms>
    <terms>murine</terms>
    <terms>in vitro</terms>
    <terms>dog</terms>
    <terms>cat</terms>
  </exclusions>
  <platform_queries>
    <pubmed>
      <scope>PubMed</scope>
      <query>(("Aged"[MeSH] OR "Aged, 80 and over"[MeSH] OR older adults[TIAB] OR elderly[TIAB] OR seniors[TIAB]) AND ("Gamification"[MeSH] OR gamification[TIAB] OR gamif*[TIAB] OR "game-based learning"[TIAB] OR "gamified training"[TIAB]) AND ("Leadership"[MeSH] OR leadership development[TIAB] OR leadership training[TIAB] OR leadership competency[TIAB] OR leader*[TIAB] skill*[TIAB]) AND (randomized controlled trial[Publication Type] OR quasi-experimental stud*[TIAB])) NOT (animals[MeSH] OR animal*[TIAB] OR rat[TIAB] OR mouse[TIAB] OR murine[TIAB])</query>
    </pubmed>
    <google_scholar>
      <scope>Google Scholar</scope>
      <query>"older adults" OR elderly OR seniors gamification OR gamified OR "game-based learning" leadership development OR training OR competency "randomized controlled trial" -animal -rats -mice</query>
    </google_scholar>
    <scopus>
      <scope>Scopus</scope>
      <query>TITLE-ABS-KEY(("older adults" OR elderly OR seniors) AND (gamif* OR "game-based learning" OR "gamified training") AND (leader* W/2 (development OR training OR competency)) AND (randomized OR quasi-experiment*) ) AND NOT TITLE-ABS-KEY(animal OR rat OR mouse OR murine)</query>
    </scopus>
    <web_of_science>
      <scope>Web of Science</scope>
      <query>TS=("older adults" OR elderly OR seniors) AND TS=(gamif* OR "game-based learning" OR "gamified training") AND TS=(leader* OR "leadership development" OR "leadership training" OR competency) AND TS=("randomized controlled trial" OR quasi-experiment*) NOT TS=(animal OR rat OR mouse OR murine)</query>
    </web_of_science>
  </platform_queries>
  <notes>
    <logic>We combined PICO components with study-design filters to narrow the scope to intervention trials and added exclusions to eliminate non-human studies. This structure yields a focused result set likely within 2–50 hits per database.</logic>
    <wildcards>Used * (e.g., gamif*, leader*) and proximity W/2 in Scopus to capture variants.</wildcards>
    <language>English</language>
    <comparison>Not applicable (null)</comparison>
  </notes>
  <metadata>
    <created_at>2024-07-04T12:00:00Z</created_at>
    <version>1.0</version>
    <author>AI Research Assistant</author>
  </metadata>
</output>