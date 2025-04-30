# Car-Damage-Detection-Vision-Agent
first using image processing to classify damaged parts and assess severity, then leveraging a large language model to generate a structured damage report. 

```
   +----------------------+       +--------------------------+       +--------------------------+
   |                      |       |                          |       |                          |
   |   (External Entity)  |       |      [Process]           |       |      [Process]           |
   |   +--------------+   |       |   +------------------+   |       |   +------------------+   |
   |   |  User Upload |---+-----> |   | Preprocess Image |---+-----> |   | Classify Damage  |   |
   |   +--------------+   | car   |   +------------------+   | parts |   +------------------+   |
   |                      | image |                          |+labels|                          |
   +----------------------+       +------------+-------------+       +-------------+------------+
                                             |                                     |
                                             | preprocessed_image                   | parts+damage_labels
                                             v                                     v
                                      +---------------+                    +----------------------+
                                      |               |                    |                      |
                                      | [Data Store]  |                    |    [Data Store]      |
                                      | Raw Image     |                    |   Damage Records     |
                                      |   Store       |                    |                      |
                                      +---------------+                    +----------------------+
                                             |                                     |
                                             | image                               | labels
                                             v                                     v
                                   +----------------------+        +--------------------------+
                                   |                      |        |                          |
                                   |      [Process]       |        |      [Process]           |
                                   |   +--------------+   |        |   +------------------+   |
                                   |   | Assess       |   | labels |   | Generate JSON    |   |
                                   |   | Severity     |---+------->|   | Output (JSON)   |   |
                                   |   +--------------+   |        |   +------------------+   |
                                   +----------------------+        +-------------+------------+
                                                                                  |
                                                                                  | damage.json
                                                                                  v
                                                                          +---------------+
                                                                          |               |
                                                                          | [Process]     |
                                                                          | LLM Report    |
                                                                          | Generator     |
                                                                          | (e.g., Gemma) |
                                                                          +---------------+
                                                                                  |
                                                                                  | text_report
                                                                                  v
                                                                          +----------------+
                                                                          | (External      |
                                                                          |   Entity)      |
                                                                          |   User Views   |
                                                                          |    Report      |
                                                                          +----------------+

```
