Music-to-Insight EDA converts raw music-industry and streaming data into actionable insights through a full end-to-end analytics pipeline. Across three phases—Data Analyst, Data Scientist, and ML Engineer—we ingest external sources, clean and explore them, engineer features, train predictive models, and ship clear reports and deployable artifacts for stakeholders.

<code>```
                                 +-------------------------------+
                                 |        External Sources       |
                                 |    (APIs / CSVs / SQL dumps)  |
                                 +---------------+---------------+
                                                 | 1. ingest
+-------------------------------+                |
|        src/data/              |                |
|        load_data.py           |                |
+---------------+---------------+                |
                | 2. clean & validate            |
                v                                v
+-------------------------------+    +-------------------------------+
|        data/raw/              |    |        data/external/        |
|    (source of truth)          |    |     (immutable snapshots)     |
+---------------+---------------+    +---------------+---------------+
                | 3. tidy tables                    |
                v                                   |
+-------------------------------+                   |
|       data/processed/         |<------------------+
|        (clean data)           |
+---------------+---------------+
                | 4. explore
                v
+-------------------------------+                 +-------------------------------+
|        notebooks/             |                 |       src/data/               |
|      01_eda.ipynb …           |                 |     process_data.py           |
+---------------+---------------+                 +---------------+---------------+
                | 5. visuals                                       |
                |                                                  v
+-------------------------------+                 +-------------------------------+
|          reports/             |<----- store ----|          figures/             |
|           eda.md              |                 |        (PNG / SVG)            |
+---------------+---------------+                 +---------------+---------------+
                | 6. insights                                      |
                v                                                  v
+-------------------------------+                 +-------------------------------+
|       src/features/           |---- 7. tests -->|            tests/             |
|     build_features.py         |                 |            pytest             |
+---------------+---------------+                 +-------------------------------+
                |
                | 8. model training
                v
+-------------------------------+
|        src/models/            |
|       train_model.py          |
+---------------+---------------+
                | 9. metrics & artifacts
                v
+-------------------------------+
|      reports/models/          |
|        model_card.md          |
+-------------------------------+

</code>
