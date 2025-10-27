<?xml version="1.0" encoding="UTF-8" standalone="yes"?>
<output>
  <topic>Impact of Artificial Intelligence on Leadership in Entrepreneurs and Student Startups</topic>
  <pico>
    <population>
      <label>Entrepreneurs and student startup founders</label>
      <mesh>Entrepreneurs</mesh>
      <mesh>Students</mesh>
      <mesh>Small Business</mesh>
      <text_words>entrepreneur*</text_words>
      <text_words>startup founder*</text_words>
      <text_words>student entrepreneur*</text_words>
      <text_words>student startup*</text_words>
      <text_words>new venture*</text_words>
      <text_words>nascent entrepreneur*</text_words>
    </population>
    <intervention_exposure>
      <label>Artificial Intelligence technologies</label>
      <mesh>Artificial Intelligence</mesh>
      <mesh>Machine Learning</mesh>
      <text_words>artificial intelligence</text_words>
      <text_words>AI</text_words>
      <text_words>machine learning</text_words>
      <text_words>deep learning</text_words>
      <text_words>neural network*</text_words>
    </intervention_exposure>
    <comparison/>
    <outcome>
      <label>Leadership behaviours and development</label>
      <mesh>Leadership</mesh>
      <text_words>leadership</text_words>
      <text_words>leadership style*</text_words>
      <text_words>leadership development</text_words>
      <text_words>leader behavior</text_words>
      <text_words>decision-making</text_words>
      <text_words>managerial leadership</text_words>
    </outcome>
  </pico>
  <exclusions>
    <non_human>true</non_human>
    <terms>animal</terms>
    <terms>animals</terms>
    <terms>mice</terms>
    <terms>rats</terms>
    <terms>rodent</terms>
    <terms>in vivo</terms>
  </exclusions>
  <platform_queries>
    <pubmed>
      <scope>PubMed</scope>
      <query>(("Entrepreneurs"[MeSH] OR "Students"[MeSH] OR "Small Business"[MeSH] OR entrepreneur*[TIAB] OR "startup founder*"[TIAB] OR "student entrepreneur*"[TIAB] OR "student startup*"[TIAB] OR "new venture*"[TIAB] OR nascent entrepreneur*[TIAB]) AND ("Artificial Intelligence"[MeSH] OR "Machine Learning"[MeSH] OR "artificial intelligence"[TIAB] OR AI[TIAB] OR "machine learning"[TIAB] OR "deep learning"[TIAB] OR neural network*[TIAB]) AND ("Leadership"[MeSH] OR leadership[TIAB] OR "leadership style*"[TIAB] OR "leadership development"[TIAB] OR "leader behavior"[TIAB] OR "decision-making"[TIAB] OR "managerial leadership"[TIAB])) NOT ("Animals"[MeSH] NOT "Humans"[MeSH])</query>
    </pubmed>
    <google_scholar>
      <scope>Google Scholar</scope>
      <query>(entrepreneur* OR "startup founder*" OR "student entrepreneur*" OR "student startup*" OR "new venture*") ("artificial intelligence" OR AI OR "machine learning" OR "deep learning" OR "neural network*") (leadership OR "leadership style*" OR "leadership development" OR "leader behavior" OR "decision-making") -animal -animals -mice -rats</query>
    </google_scholar>
    <scopus>
      <scope>Scopus</scope>
      <query>TITLE-ABS-KEY((entrepreneur* OR "startup founder*" OR "student entrepreneur*" OR "student startup*" OR "new venture*" OR nascent entrepreneur*) AND ("artificial intelligence" OR AI OR "machine learning" OR "deep learning" OR neural network*) AND (leadership OR "leadership style*" OR "leadership development" OR "leader behavior" OR decision-making)) AND NOT TITLE-ABS-KEY(animal OR animals OR mice OR rats OR rodent)</query>
    </scopus>
    <web_of_science>
      <scope>Web of Science</scope>
      <query>TS=(entrepreneur* OR "startup founder*" OR "student entrepreneur*" OR "student startup*" OR "new venture*" OR nascent entrepreneur*) AND TS=("artificial intelligence" OR AI OR "machine learning" OR "deep learning" OR neural network*) AND TS=(leadership OR "leadership style*" OR "leadership development" OR "leader behavior" OR decision-making) NOT TS=(animal OR animals OR mice OR rats OR rodent)</query>
    </web_of_science>
  </platform_queries>
  <notes>
    <logic>Combined Population, Intervention, and Outcome with AND; synonyms/variants grouped with OR; exclusions applied to remove non-human studies.</logic>
    <wildcards>Used * for truncation to capture word stems and variants.</wildcards>
    <language>English</language>
    <comparison>No comparator specified</comparison>
  </notes>
  <metadata>
    <created_at>2024-06-21</created_at>
    <version>1.0</version>
    <author>ChatGPT</author>
  </metadata>
</output>