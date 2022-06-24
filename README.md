# Goal
Just messing with Airflow

# Issues
Noticed that I had an issue installing apache-airflow package using `pipenv install apache`. However it worked if I used `pipenv run python install apache-airflow`. I didn't like that solution because it meant that my Pipfile was out of sync with the packages in my virtual environment.

I happened upon a solution when I noticed from the error message that the pipenv command was using a separate python interpreter than the one I thought. My solution was to expressly specify the path using the `--python` flag. Hence the command below eventually worked without issue:

```
pipenv install -r dev-requirements.txt --python <path-to-my-main-interpreter>
```
