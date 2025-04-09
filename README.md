# ai_session_graph_rag

python -m virtualenv .env  

.\.env\Scripts\activate  

pip install -r .\requirements.txt  

![GraphRAG Help](./img/graphrag_help.png)

graphrag init --root ./ragtest

update env file

update settings.yaml

graphrag prompt-tune --root .\ragtest --config .\ragtest\settings.yaml --domain "observability infrastructure logging" --selection-method auto --max-tokens 30000 --min-examples-required 3 --language ENGLISH --discover-entity-types --output .\ragtest\auto_tuned_prompt --n-subset-max 100

update path of prompts for entity_extraction, summarize_descriptions and community_reports in settings.yaml

graphrag prompt-tune --root .\nobel_prize_physics_2024 --config .\nobel_prize_physics_2024\settings.yaml --selection-method auto --k 5 --max-tokens 30000 --min-examples-required 2 --discover-entity-types --output .\nobel_prize_physics_2024\auto_tuned_prompt

graphrag query --root .\nobel_prize_physics_2024 --method global --query "How does artificial intelligence helps in physics?"

graphrag query --root .\nobel_prize_physics_2024 --method global --query "Who won nobel prize in physics in the year 2024?"

graphrag query --root .\nobel_prize_physics_2024 --method global --query "Who is John J. Hopfield?"