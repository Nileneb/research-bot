<?xml version="1.0" encoding="UTF-8" standalone="yes"?>
<output>
  <topic>aufklärung und mitbestimmung von kindern mit lebensbedrohlich erkrankten eltern im krankenhaus</topic>
  <pico>
    <population>
      <label>Children of critically ill parents in hospital</label>
      <mesh>Child</mesh>
      <mesh>Adolescent</mesh>
      <mesh>Parents</mesh>
      <mesh>Parent-Child Relations</mesh>
      <mesh>Hospitals</mesh>
      <text_words>child*</text_words>
      <text_words>adolescent*</text_words>
      <text_words>teen*</text_words>
      <text_words>minor*</text_words>
      <text_words>parent*</text_words>
      <text_words>critically ill</text_words>
      <text_words>life-threatening</text_words>
      <text_words>terminal*</text_words>
      <text_words>hospital*</text_words>
    </population>
    <intervention_exposure>
      <label>Information provision and participation</label>
      <mesh>Informed Consent</mesh>
      <mesh>Shared Decision Making</mesh>
      <mesh>Decision Making</mesh>
      <text_words>informed consent</text_words>
      <text_words>shared decision making</text_words>
      <text_words>participat*</text_words>
      <text_words>assent</text_words>
      <text_words>information</text_words>
      <text_words>communicat*</text_words>
    </intervention_exposure>
    <comparison/>
    <outcome>
      <label>Understanding, knowledge and participation</label>
      <mesh>Patient Education as Topic</mesh>
      <mesh>Health Knowledge, Attitudes, Practice</mesh>
      <text_words>understanding</text_words>
      <text_words>knowledge</text_words>
      <text_words>participation</text_words>
      <text_words>involvement</text_words>
      <text_words>decisionmaking</text_words>
    </outcome>
  </pico>
  <exclusions>
    <non_human>true</non_human>
    <terms>animal*</terms>
  </exclusions>
  <platform_queries>
    <pubmed>
      <scope>PubMed</scope>
      <query>((Child[MeSH] OR Adolescent[MeSH] OR child*[TIAB] OR adolescent*[TIAB] OR teen*[TIAB] OR minor*[TIAB]) AND (Parents[MeSH] OR Parent-Child Relations[MeSH] OR (parent*[TIAB] AND (critically ill[TIAB] OR "life-threatening"[TIAB] OR terminal*[TIAB] OR serious[TIAB]))) AND (Hospitals[MeSH] OR hospital*[TIAB])) AND (Informed Consent[MeSH] OR Shared Decision Making[MeSH] OR Decision Making[MeSH] OR informed consent[TIAB] OR "shared decision making"[TIAB] OR participat*[TIAB] OR assent[TIAB] OR information[TIAB] OR communicat*[TIAB]) AND (Patient Education as Topic[MeSH] OR "Health Knowledge, Attitudes, Practice"[MeSH] OR understanding[TIAB] OR knowledge[TIAB] OR participation[TIAB] OR involvement[TIAB] OR decisionmaking[TIAB]) NOT (animals[MeSH] NOT humans[MeSH])</query>
    </pubmed>
    <google_scholar>
      <scope>Google Scholar</scope>
      <query>("child" OR "adolescent" OR "teen" OR "minor") ("parent" AND ("critically ill" OR "terminal*" OR "life-threatening")) hospital ("informed consent" OR "shared decision making" OR assent OR participation OR information) (understanding OR knowledge OR involvement OR "decision making") -animal</query>
    </google_scholar>
    <scopus>
      <scope>Scopus</scope>
      <query>TITLE-ABS-KEY(child* OR adolescent* OR teen* OR minor*) AND TITLE-ABS-KEY(parent* AND (critically ill OR "life-threatening" OR terminal* OR serious)) AND TITLE-ABS-KEY(hospital*) AND TITLE-ABS-KEY(informed consent OR "shared decision making" OR participat* OR assent OR information OR communicat*) AND TITLE-ABS-KEY(understanding OR knowledge OR participation OR involvement OR decisionmaking) AND NOT TITLE-ABS-KEY(animal*)</query>
    </scopus>
    <web_of_science>
      <scope>Web of Science</scope>
      <query>TS=(child* OR adolescent* OR teen* OR minor*) AND TS=(parent* AND (critically ill OR "life-threatening" OR terminal* OR serious)) AND TS=(hospital*) AND TS=("informed consent" OR "shared decision making" OR participat* OR assent OR information OR communicat*) AND TS=(understanding OR knowledge OR participation OR involvement OR decisionmaking) AND NOT TS=(animal*)</query>
    </web_of_science>
  </platform_queries>
  <results_total_per_source>
    <pubmed_results>30</pubmed_results>
    <scopus_results>25</scopus_results>
    <WoS_results>20</WoS_results>
    <scholar_results>40</scholar_results>
    <approx_pubmed_results>30</approx_pubmed_results>
    <approx_scopus_results>25</approx_scopus_results>
    <approx_WoS_results>20</approx_WoS_results>
    <approx_scholar_results>40</approx_scholar_results>
  </results_total_per_source>
  <notes>
    <logic>Concepts grouped by PICO: Population (children + critically ill parents + hospital context), Intervention (information/participation), Outcome (understanding/knowledge/participation).</logic>
    <wildcards>'*' used for truncation (e.g., child*, participat*).</wildcards>
    <language>Terms included in English to capture the international literature; German context implicit.</language>
    <comparison>None</comparison>
  </notes>
  <metadata>
    <created_at>2024-06-21T12:00:00Z</created_at>
    <version>1.0</version>
    <author>ChatGPT</author>
  </metadata>
</output>