<?xml version="1.0" encoding="UTF-8" standalone="yes"?>
<output>
  <topic>Impact of AI-based Leadership on Performance of Student Startups</topic>
  <pico>
    <population>
      <label>Student entrepreneurs or student startups</label>
      <mesh>Students</mesh>
      <mesh>Entrepreneurship</mesh>
      <text_words>student entrepreneur*</text_words>
      <text_words>student startup*</text_words>
      <text_words>university entrepreneur*</text_words>
      <text_words>collegiate startup*</text_words>
    </population>
    <intervention_exposure>
      <label>AI-based leadership</label>
      <mesh>Artificial Intelligence</mesh>
      <mesh>Leadership</mesh>
      <text_words>artificial intelligence</text_words>
      <text_words>AI</text_words>
      <text_words>machine learning</text_words>
      <text_words>digital leadership</text_words>
      <text_words>AI-driven leadership</text_words>
    </intervention_exposure>
    <comparison/>
    <outcome>
      <label>Startup performance and success</label>
      <mesh>Innovation</mesh>
      <text_words>innovation</text_words>
      <text_words>performance</text_words>
      <text_words>success</text_words>
      <text_words>growth</text_words>
      <text_words>sustainability</text_words>
    </outcome>
  </pico>
  <exclusions>
    <non_human>true</non_human>
    <terms>animal</terms>
    <terms>animals</terms>
    <terms>anim*</terms>
  </exclusions>
  <platform_queries>
    <pubmed>
      <scope>MeSH + Title/Abstract</scope>
      <query>(("Students"[MeSH] OR student[TIAB] OR university[TIAB] OR collegiate[TIAB] OR "Entrepreneurship"[MeSH] OR entrepreneur*[TIAB] OR "startup*"[TIAB]) AND ("Artificial Intelligence"[MeSH] OR "artificial intelligence"[TIAB] OR AI[TIAB] OR "machine learning"[TIAB]) AND ("Leadership"[MeSH] OR leadership[TIAB] OR manager*[TIAB] OR "digital leadership"[TIAB] OR "AI-driven leadership"[TIAB]) AND ("Innovation"[MeSH] OR innovation[TIAB] OR performance[TIAB] OR success[TIAB] OR growth[TIAB] OR sustainability[TIAB])) AND NOT animals[MeSH]</query>
    </pubmed>
    <google_scholar>
      <scope>Keywords (≤250 chars)</scope>
      <query>("student entrepreneur" OR "student startup") ("artificial intelligence" OR AI) (leadership) (performance OR success OR innovation) -animal</query>
    </google_scholar>
    <scopus>
      <scope>Title/Abstract/Keywords</scope>
      <query>TITLE-ABS-KEY((student entrepreneur* OR student startup* OR universit* entrepreneur* OR collegiat* startup*) AND ("artificial intelligence" OR ai OR "machine learning") AND (leadership OR manag* OR "digital leadership" OR "ai-driven leadership") AND (innovation OR performance OR success OR growth OR sustainab*)) AND NOT TITLE-ABS-KEY(anim* OR animal*)</query>
    </scopus>
    <web_of_science>
      <scope>Topic</scope>
      <query>TS=((student entrepreneur* OR student startup* OR universit* entrepreneur* OR collegiat* startup*) AND ("artificial intelligence" OR ai OR "machine learning") AND (leadership OR manage* OR "digital leadership" OR "ai-driven leadership") AND (innovation OR performance OR success OR growth OR sustainab*)) NOT (anim* OR animal*)</query>
    </web_of_science>
  </platform_queries>
  <notes>
    <logic>Synonyms grouped with OR within each PICO component; components combined with AND; non-human studies excluded with NOT.</logic>
    <wildcards>* for truncation of word stems</wildcards>
    <language>English</language>
    <comparison>None</comparison>
  </notes>
  <metadata>
    <created_at>2024-07-10</created_at>
    <version>1.0</version>
    <author>AI research assistant</author>
    <query>How does AI-based leadership impact the performance of student startups?</query>
    <results_total_per_source>
      <pubmed_results>n/a</pubmed_results>
      <scopus_results>n/a</scopus_results>
      <WoS_results>n/a</WoS_results>
      <scholar_results>n/a</scholar_results>
    </results_total_per_source>
  </metadata>
</output>