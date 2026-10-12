# Interactive graphics examples

Run these commands from the repository root with the dependencies from
`requirements.txt` installed. Data paths in the Python apps are relative to the
script, so they also work from other working directories. The Plotly notebooks
find the `data/` folder in the current directory or its parents; open them from
within this repository.

| Example | Concept | Solution |
| --- | --- | --- |
| Flask | `python 06_interactive_graphics/flask_example/concept_flask.py` | `python 06_interactive_graphics/flask_example/solution_flask.py` |
| FastAPI | `python -m uvicorn concept_fastapi:app --app-dir 06_interactive_graphics/fastapi_example --host 0.0.0.0 --port 8000` | `python -m uvicorn solution_fastapi:app --app-dir 06_interactive_graphics/fastapi_example --host 0.0.0.0 --port 8000` |
| Streamlit | `python -m streamlit run 06_interactive_graphics/streamlit_example/concept_streamlit.py --server.address 0.0.0.0` | `python -m streamlit run 06_interactive_graphics/streamlit_example/solution_streamlit.py --server.address 0.0.0.0` |

Run one app per port: Flask uses 5000, FastAPI uses 8000, and Streamlit uses 8501.
Open the corresponding forwarded port in Codespaces. FastAPI's interactive API
documentation is at `/docs`; try `/histogram` and `/summary` there. The FastAPI
solution also exposes `/top-cities` and `/power-types`.

Open and run the notebooks in `plotly_example/` with Jupyter. The concept
notebook includes Dash source code that can be copied to a standalone Python
script and run from within the repository (`http://127.0.0.1:8050`).

The `exercise_*` files intentionally contain `YOUR CODE HERE` placeholders.
They are assignment templates; use the matching `solution_*` files to run the
completed EV charging station examples.

## Code style

Python code uses PEP 8 formatting with a maximum line length of 79 characters.
To check the Python scripts from the repository root:

```bash
python -m pip install pylint pycodestyle
python -m pylint --rcfile=06_interactive_graphics/.pylintrc 06_interactive_graphics/*/*.py
python -m pycodestyle 06_interactive_graphics/*/*.py
```

The local pylint configuration disables only duplicate-code checks because the
concepts, exercises and solutions intentionally repeat teaching examples.
Exercise scaffolds retain their existing unused-import/unused-argument exceptions
for imports and parameters that students will use when completing the tasks.
Notebook code cells and the embedded Dash source follow the same formatting.
