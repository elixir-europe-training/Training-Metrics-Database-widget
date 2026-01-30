# Training Metrics Databse widgets

This is the github repo for the official TMD widgets and user instructions

## Summary statistics widget

This widget allows users to incorporate summary statistics charts into their own websites. Any changes in the TMD will then be reflected automatically on the users website. 

### Setup

Add the following code snippets to your own website:

Insert the below snippet where on the website you want the widget to be: 
``` 
<div class="tmd-widget" id="tmd-widget-container"></div>
```

Place this code snippet in the bottom or top of your code:

```
<script src="https://elixir-europe-training.github.io/Training-Metrics-Database-widget/widget.js"></script>
<script>
  TMDWidget({
    container: '#tmd-widget-container',
    questions: [<question_slug>, <question_slug>],
  }).catch((error) => {
    console.error('TMDWidget failed to initialise', error);
  });
</script>
```

The following parameters are customizable for the widget:

* questions: A list of question slug ids for displaying. You can find the question slug in the admin panel in the TMD. If defined, questions are displayed in the order they are inputed.
* questionSets: A list of questionSets for displaying. If defined, all questions in the questionSet will be displayed. questionSets are listed by their slug.

Either questionSets can be set, or questions, not both. In case of both
being defined, questionSets take precedence. If neither questionSets nor questions
are defined, all questionSets will be returned.

* chartType: Define what chart type results should be shown in. Valid choices
are 'pie' and 'bar'. Defaults to 'pie' if not defined.
* colors: A list of hex colors to be used for plotting. Defaults to ELIXIR colors
* endpoint: The API endpoint to get the data from. Defaults
to "https://tmd.elixir-europe.org/metrics"