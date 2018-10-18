---
layout: page
title:  Chapter 5.3 - Invoice
product: communications
doctype: comms_dev_guide
chapter: reference
nav: apis
disqus: 0
---

<ul class="pager">
  <li class="previous"><a href="/communications/dev-guide/reference/company-data/"><i class="glyphicon glyphicon-chevron-left"></i>Previous</a></li>
  <li class="next"><a href="/communications/dev-guide/reference/location/">Next<i class="glyphicon glyphicon-chevron-right"></i></a></li>
</ul>

<h3>Invoice</h3>

The <code>Invoice</code> object contains information about one or more <b>transactions</b>:

<div class="mobile-table">
  <table class="styled-table">
    <thead>
      <tr>
        <th>Key</th>
        <th>Value</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td><code>doc</code></td>
        <td><code>[string]</code> Document Code
        <br>
          The Document Code is a unique string that is used to <a class="dev-guide-link" href="/communications/dev-guide/commit-uncommit/">Commit or Uncommit</a> transactions.
        </td>
      </tr>
      <tr>
        <td><code>cmmt</code></td>
        <td><code>[bool]</code> Commit
          <ul class="dev-guide-list">
            <li><code>true</code>: The transaction should be <a class="dev-guide-link" href="/communications/dev-guide/commit-uncommit/">committed</a></li>
            <li><code>false</code>: The transaction should be <a class="dev-guide-link" href="/communications/dev-guide/commit-uncommit/">uncommitted</a></li>
          </ul>
        </td>
      </tr>
      <tr>
        <td><code>bill</code></td>
        <td><a class="dev-guide-link" href="/communications/dev-guide/reference/location/"><code>[Location]</code></a> Bill To Location
          <br>
          There are several ways to input location information. See the <a class="dev-guide-link" href="/communications/dev-guide/reference/location/">Location</a> section for more details.
        </td>
      </tr>
      <tr>
        <td><code>cust</code></td>
        <td><code>[int]</code> Customer Type
          <br>
          <ul class="dev-guide-list">
            <li><code>0</code>: Residential</li>
            <li><code>1</code>: Business</li>
            <li><code>2</code>: Senior Citizen</li>
            <li><code>3</code>: Industrial</li>
          </ul>
        </td>
      </tr>
      <tr>
        <td><code>lfln</code></td>
        <td><code>[bool]</code> Lifeline
          <ul class="dev-guide-list">
            <li><code>true</code>: The customer is a lifeline participant</li>
            <li><code>false</code>: The customer is not a lifeline participant</li>
          </ul>
          Lifeline is a federal program that subsidizes the cost of phone and internet for eligible customers.
        </td>
      </tr>
      <tr>
        <td><code>date</code></td>
        <td><code>[timestamp]</code> Date
          <br>
          <i>ex.</i><code> 2009-12-01T03:00:00</code>
          <br>
          The date when the transaction took place. <b>An accurate timestamp in this field is important!</b> This will affect the rules our tax engine applies when calculating taxes. 
          <br>
          <br>
          For example, if you submit a CalcTaxes request with a <code>date</code> of <code>7/1/2018</code>, our tax engine will use the rules that apply for your jurisdiction on <code>7/1/2018</code>. If the transaction <i>actually</i> occurred on <code>7/25/2018</code>, and the tax rate for this transaction changed after <code>7/1/2018</code>, you may receive incorrect tax information.
        </td>
      </tr>
      <tr>
        <td><code>exms</code></td>
        <td><a class="dev-guide-link" href="/communications/dev-guide/reference/exemption/"><code>[Exemption]</code></a> <span class="t5">optional</span> Exemptions
          <br>
          A list of <a class="dev-guide-link" href="/communications/dev-guide/reference/exemption/">Exemptions</a> to apply to this transaction.
        </td>
      </tr>
      <tr>
        <td><code>itms</code></td>
        <td><a class="dev-guide-link" href="/communications/dev-guide/reference/line-item/"><code>[LineItems]</code></a> Line Items
          <br>
          A list of <a class="dev-guide-link" href="/communications/dev-guide/reference/line-items/">Line Items</a> to process for this transaction.
        </td>
      </tr>
    </tbody>
  </table>
</div>
<br>

<h3>Example</h3>

{% highlight json %}
"inv": [
    {
      "doc": "DocumentCode12345",
      "cmmt": true,
      "bill": {
        // Location
      },
      "cust": 0,
      "lfln": true,
      "date": "2018-09-23T20:31:53.452Z",
      "exms": [
        {
          // Exemptions
        }
      ],
      "itms": [
        {
          // Line Items
        }
      ],

{% endhighlight %}

<ul class="pager">
  <li class="previous"><a href="/communications/dev-guide/reference/company-data/"><i class="glyphicon glyphicon-chevron-left"></i>Previous</a></li>
  <li class="next"><a href="/communications/dev-guide/reference/location/">Next<i class="glyphicon glyphicon-chevron-right"></i></a></li>
</ul>