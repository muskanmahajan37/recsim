<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="recsim.choice_model.CascadeChoiceModel" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="choose_item"/>
<meta itemprop="property" content="score_documents"/>
</div>

# recsim.choice_model.CascadeChoiceModel

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">

</table>

<a target="_blank" href="https://github.com/google-research/recsim/tree/master/recsim/choice_model.py">View
source</a>

The base class for cascade choice models.

Inherits From:
[`NormalizableChoiceModel`](../../recsim/choice_model/NormalizableChoiceModel.md)

<pre class="devsite-click-to-copy prettyprint lang-py tfo-signature-link">
<code>recsim.choice_model.CascadeChoiceModel(
    choice_features
)
</code></pre>

<!-- Placeholder for "Used in" -->

<!-- Tabular view -->

 <table class="responsive fixed orange">
<colgroup><col width="214px"><col></colgroup>
<tr><th colspan="2"><h2 class="add-link">Raises</h2></th></tr>

<tr>
<td>
`ValueError`
</td>
<td>
if either attention_prob or base_attention_prob is invalid.
</td>
</tr>
</table>

<!-- Tabular view -->

 <table class="responsive fixed orange">
<colgroup><col width="214px"><col></colgroup>
<tr><th colspan="2"><h2 class="add-link">Attributes</h2></th></tr>

<tr> <td> `attention_prob` </td> <td> The probability of examining a document i
given document i - 1 not clicked. </td> </tr><tr> <td> `score_scaling` </td>
<td> A multiplicative factor to convert score of document i to the click
probability of examined document i. </td> </tr><tr> <td> `score_no_click` </td>
<td>

</td> </tr><tr> <td> `scores` </td> <td>

</td>
</tr>
</table>

## Methods

<h3 id="choose_item"><code>choose_item</code></h3>

<a target="_blank" href="https://github.com/google-research/recsim/tree/master/recsim/choice_model.py">View
source</a>

<pre class="devsite-click-to-copy prettyprint lang-py tfo-signature-link">
<code>choose_item()
</code></pre>

Returns selected index of document in the slate.

<!-- Tabular view -->

 <table class="responsive fixed orange">
<colgroup><col width="214px"><col></colgroup>
<tr><th colspan="2">Returns</th></tr>

<tr>
<td>
`selected_index`
</td>
<td>
a integer indicating which item was chosen, or None if
none were selected.
</td>
</tr>
</table>

<h3 id="score_documents"><code>score_documents</code></h3>

<a target="_blank" href="https://github.com/google-research/recsim/tree/master/recsim/choice_model.py">View
source</a>

<pre class="devsite-click-to-copy prettyprint lang-py tfo-signature-link">
<code>@abc.abstractmethod</code>
<code>score_documents(
    user_state, doc_obs
)
</code></pre>

Computes unnormalized scores of documents in the slate given user state.

<!-- Tabular view -->

 <table class="responsive fixed orange">
<colgroup><col width="214px"><col></colgroup>
<tr><th colspan="2">Args</th></tr>

<tr>
<td>
`user_state`
</td>
<td>
An instance of AbstractUserState.
</td>
</tr><tr>
<td>
`doc_obs`
</td>
<td>
A numpy array that represents the observation of all documents in
the slate.
</td>
</tr>
</table>

<!-- Tabular view -->

 <table class="responsive fixed orange">
<colgroup><col width="214px"><col></colgroup>
<tr><th colspan="2">Attributes</th></tr>

<tr>
<td>
`scores`
</td>
<td>
A numpy array that stores the scores of all documents.
</td>
</tr><tr>
<td>
`score_no_click`
</td>
<td>
A float that represents the score for the action of
picking no document.
</td>
</tr>
</table>
