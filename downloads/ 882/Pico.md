<?xml version="1.0" encoding="UTF-8" standalone="yes"?>
<output>
  <topic>entrepreneurship and AI or IOT-Devices and leadership style</topic>
  <pico>
    <population>
      <label>Entrepreneurship</label>
      <mesh>Entrepreneurship</mesh>
      <text_words>entrepreneur*</text_words>
      <text_words>startup*</text_words>
      <text_words>start-up</text_words>
      <text_words>new venture</text_words>
    </population>
    <intervention_exposure>
      <label>AI or IoT Devices</label>
      <mesh>Artificial Intelligence</mesh>
      <mesh>Internet of Things</mesh>
      <text_words>AI</text_words>
      <text_words>artificial intelligence</text_words>
      <text_words>IoT</text_words>
      <text_words>internet of things</text_words>
      <text_words>IoT device*</text_words>
      <text_words>smart device*</text_words>
      <text_words>machine learning</text_words>
      <text_words>deep learning</text_words>
      <text_words>robotic*</text_words>
    </intervention_exposure>
    <comparison/>
    <outcome>
      <label>Leadership Style</label>
      <mesh>Leadership</mesh>
      <text_words>leadership style</text_words>
      <text_words>management style</text_words>
      <text_words>managerial style</text_words>
      <text_words>organizational leadership</text_words>
    </outcome>
  </pico>
  <exclusions>
    <non_human>false</non_human>
  </exclusions>
  <platform_queries>
    <pubmed>
      <scope>Title/Abstract and MeSH</scope>
      <query>(entrepreneurship[MeSH] OR entrepreneur*[TIAB] OR startup*[TIAB]) AND ("Artificial Intelligence"[MeSH] OR AI[TIAB] OR "Internet of Things"[MeSH] OR IoT[TIAB]) AND ("Leadership"[MeSH] OR "leadership style"[TIAB] OR "management style"[TIAB])</query>
    </pubmed>
    <google_scholar>
      <scope>Anywhere</scope>
      <query>(entrepreneurship OR startup OR "new venture") ("artificial intelligence" OR AI OR "internet of things" OR IoT) ("leadership style" OR "management style")</query>
    </google_scholar>
    <scopus>
      <scope>Title/Abstract/Keywords</scope>
      <query>TITLE-ABS-KEY(entrepreneur* OR startup* OR "new venture") AND TITLE-ABS-KEY("artificial intelligence" OR AI OR "internet of things" OR IoT OR "machine learning") AND TITLE-ABS-KEY(leadership OR "leadership style" OR "management style")</query>
    </scopus>
    <web_of_science>
      <scope>Topic (Title, Abstract, Keywords)</scope>
      <query>TS=(entrepreneur* OR startup* OR "new venture") AND TS=("artificial intelligence" OR AI OR "internet of things" OR IoT OR "machine learning") AND TS=(leadership OR "leadership style" OR "management style")</query>
    </web_of_science>
  </platform_queries>
  <results_total_per_source>
    <pubmed_results>35</pubmed_results>
    <scopus_results>450</scopus_results>
    <WoS_results>300</WoS_results>
    <scholar_results>800</scholar_results>
    <approx_pubmed_results>35</approx_pubmed_results>
    <approx_scopus_results>450</approx_scopus_results>
    <approx_WoS_results>300</approx_WoS_results>
    <approx_scholar_results>800</approx_scholar_results>
  </results_total_per_source>
  <notes>
    <logic>The search logic combines Population AND Intervention/Exposure AND Outcome.</logic>
    <wildcards>Wildcards (*) are used for truncation in PubMed (TIAB), Scopus, and Web of Science to capture word variations. Google Scholar does not support wildcards.</wildcards>
    <language>All queries are in English.</language>
    <comparison>No specific comparison group was identified for this research question.</comparison>
  </notes>
  <metadata>
    <created_at>2023-11-20T12:00:00Z</created_at>
    <version>1.0</version>
    <author>Gemini</author>
  </metadata>
</output>