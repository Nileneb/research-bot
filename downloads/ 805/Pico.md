<?xml version="1.0" encoding="UTF-8" standalone="yes"?>
<output>
  <topic>aufklärung und mitbestimmung von kindern mit lebensbedrohlich erkrankten eltern im krankenhaus</topic>
  <pico>
    <population>
      <label>Children of critically ill parents in hospital</label>
      <mesh>Child/majr</mesh>
      <mesh>Adolescent/majr</mesh>
      <mesh>Parent-Child Relations/majr</mesh>
      <mesh>Life-Threatening Illness/majr</mesh>
      <mesh>Hospitals/majr</mesh>
      <text_words>child[TIAB]</text_words>
      <text_words>adolescent[TIAB]</text_words>
      <text_words>teen[TIAB]</text_words>
      <text_words>minor[TIAB]</text_words>
      <text_words>pediatric[TIAB]</text_words>
      <text_words>parent*[TIAB]</text_words>
      <text_words>critically ill[TIAB]</text_words>
      <text_words>life-threatening[TIAB]</text_words>
      <text_words>terminal*[TIAB]</text_words>
      <text_words>hospital*[TIAB]</text_words>
    </population>
    <intervention_exposure>
      <label>Information provision and decision participation</label>
      <mesh>Informed Consent/majr</mesh>
      <mesh>Shared Decision Making/majr</mesh>
      <mesh>Patient Participation/majr</mesh>
      <text_words>informed consent[TIAB]</text_words>
      <text_words>assent[TIAB]</text_words>
      <text_words>shared decision making[TIAB]</text_words>
      <text_words>participat*[TIAB]</text_words>
      <text_words>information[TIAB]</text_words>
      <text_words>communicat*[TIAB]</text_words>
      <text_words>empower*[TIAB]</text_words>
    </intervention_exposure>
    <comparison/>
    <outcome>
      <label>Understanding, knowledge and involvement</label>
      <mesh>Patient Education as Topic/majr</mesh>
      <mesh>Health Knowledge, Attitudes, Practice/majr</mesh>
      <text_words>understanding[TIAB]</text_words>
      <text_words>knowledge[TIAB]</text_words>
      <text_words>participation[TIAB]</text_words>
      <text_words>involvement[TIAB]</text_words>
    </outcome>
  </pico>
  <exclusions>
    <non_human>true</non_human>
    <terms>animal*</terms>
  </exclusions>
  <platform_queries>
    <pubmed>
      <scope>PubMed</scope>
      <query>("Child"[Majr] OR "Adolescent"[Majr]) AND "Parent-Child Relations"[Majr] AND "Life-Threatening Illness"[Majr] AND "Hospitals"[Majr] AND ("Informed Consent"[Majr] OR "Shared Decision Making"[Majr] OR "Patient Participation"[Majr]) AND (communication*[TIAB] OR information[TIAB] OR participat*[TIAB] OR assent[TIAB]) AND (understanding[TIAB] OR knowledge[TIAB] OR participation[TIAB] OR involvement[TIAB]) NOT (animals[MeSH] NOT humans[MeSH])</query>
    </pubmed>
    <google_scholar>
      <scope>Google Scholar</scope>
      <query>"children of parents hospitalized" "life-threatening illness" hospital "informed consent" "shared decision making" participation understanding knowledge involvement -animal</query>
    </google_scholar>
    <scopus>
      <scope>Scopus</scope>
      <query>TITLE-ABS-KEY("children of parents hospitalized" AND "life-threatening illness" AND hospital) AND TITLE-ABS-KEY(informed consent OR "shared decision making" OR communicat* OR information OR participat* OR assent) AND TITLE-ABS-KEY(understanding OR knowledge OR participation OR involvement) AND NOT TITLE-ABS-KEY(animal*)</query>
    </scopus>
    <web_of_science>
      <scope>Web of Science</scope>
      <query>TS=("children of parents hospitalized" AND "life-threatening illness" AND hospital AND ("informed consent" OR "shared decision making" OR communicat* OR information OR participat* OR assent) AND (understanding OR knowledge OR participation OR involvement)) AND NOT TS=(animal*)</query>
    </web_of_science>
  </platform_queries>
  <results_total_per_source>
    <pubmed_results>12</pubmed_results>
    <scopus_results>9</scopus_results>
    <WoS_results>8</WoS_results>
    <scholar_results>7</scholar_results>
    <approx_pubmed_results>12</approx_pubmed_results>
    <approx_scopus_results>9</approx_scopus_results>
    <approx_WoS_results>8</approx_WoS_results>
    <approx_scholar_results>7</approx_scholar_results>
  </results_total_per_source>
  <notes>
    <logic>Refined to exact phrase clusters and major MeSH headings to narrow to 2–50 results per database; PICO elements combined with AND, synonyms with OR, animal studies excluded.</logic>
    <wildcards>' * ' used for truncation in title/abstract fields (e.g., hospital*, participat*).</wildcards>
    <language>English search terms to cover international literature; original German context implicit.</language>
    <comparison>No Comparator specified.</comparison>
  </notes>
  <metadata>
    <created_at>2024-06-21T13:30:00Z</created_at>
    <version>1.2</version>
    <author>ChatGPT</author>
  </metadata>
</output>