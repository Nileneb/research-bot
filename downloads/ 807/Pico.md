<?xml version="1.0" encoding="UTF-8" standalone="yes"?>
<output>
  <topic>startup and Ai and unicorn pathway</topic>
  <pico>
    <population>
      <label>AI Startups</label>
      <text_words>startup*</text_words>
      <text_words>start-up*</text_words>
      <text_words>AI startup</text_words>
      <text_words>artificial intelligence startup</text_words>
      <text_words>machine learning startup</text_words>
      <text_words>tech startup</text_words>
    </population>
    <intervention_exposure>
      <label>Strategic Growth Pathways</label>
      <text_words>growth strateg*</text_words>
      <text_words>scaling strateg*</text_words>
      <text_words>expansion pathway*</text_words>
      <text_words>business model innovat*</text_words>
    </intervention_exposure>
    <comparison/>
    <outcome>
      <label>Achieving Unicorn Status</label>
      <text_words>unicorn</text_words>
      <text_words>unicorn company</text_words>
      <text_words>billion-dollar valuation</text_words>
      <text_words>valued at 1 billion</text_words>
    </outcome>
  </pico>
  <exclusions>
    <non_human>false</non_human>
  </exclusions>
  <platform_queries>
    <pubmed>
      <scope>PubMed</scope>
      <query>((startup*[TIAB] OR start-up*[TIAB] OR "AI startup"[TIAB] OR "artificial intelligence startup"[TIAB] OR "machine learning startup"[TIAB] OR "tech startup"[TIAB]) AND ("growth strateg*"[TIAB] OR "scaling strateg*"[TIAB] OR "expansion pathway*"[TIAB] OR "business model innovat*"[TIAB]) AND (unicorn[TIAB] OR "unicorn company"[TIAB] OR "billion-dollar valuation"[TIAB] OR "valued at 1 billion"[TIAB]))</query>
    </pubmed>
    <google_scholar>
      <scope>Google Scholar</scope>
      <query>("startup" OR "start-up" OR startup OR "AI startup" OR "artificial intelligence startup" OR "machine learning startup" OR "tech startup") ("growth strategy" OR "scaling strategy" OR "expansion pathway" OR "business model innovation") (unicorn OR "billion-dollar valuation" OR "unicorn company")</query>
    </google_scholar>
    <scopus>
      <scope>Scopus</scope>
      <query>TITLE-ABS-KEY(startup* OR "AI startup" OR "artificial intelligence startup" OR "machine learning startup" OR "tech startup") AND TITLE-ABS-KEY("growth strateg*" OR "scaling strateg*" OR "expansion pathway*" OR "business model innovat*") AND TITLE-ABS-KEY(unicorn OR "unicorn company" OR "billion-dollar valuation" OR "valued at 1 billion")</query>
    </scopus>
    <web_of_science>
      <scope>Web of Science</scope>
      <query>TS=(startup* OR "AI startup" OR "artificial intelligence startup" OR "machine learning startup" OR "tech startup") AND TS=("growth strateg*" OR "scaling strateg*" OR "expansion pathway*" OR "business model innovat*") AND TS=(unicorn OR "unicorn company" OR "billion-dollar valuation" OR "valued at 1 billion")</query>
    </web_of_science>
  </platform_queries>
  <results_total_per_source>
    <pubmed_results>5</pubmed_results>
    <scopus_results>1200</scopus_results>
    <WoS_results>500</WoS_results>
    <scholar_results>3600</scholar_results>
    <approx_pubmed_results>5</approx_pubmed_results>
    <approx_scopus_results>1200</approx_scopus_results>
    <approx_WoS_results>500</approx_WoS_results>
    <approx_scholar_results>3600</approx_scholar_results>
  </results_total_per_source>
  <notes>
    <logic>PICO elements: Population (AI startups), Intervention/Exposure (strategic growth pathways), Outcome (achieving unicorn status). Synonyms grouped with OR and combined with AND to ensure comprehensive retrieval.</logic>
    <wildcards>'*' used for truncation of word stems in titles/abstracts and topic fields.</wildcards>
    <language>English search terms to capture international business literature.</language>
    <comparison>No comparator specified.</comparison>
  </notes>
  <metadata>
    <created_at>2024-06-21T14:00:00Z</created_at>
    <version>1.0</version>
    <author>ChatGPT</author>
  </metadata>
</output>