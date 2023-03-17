# QUIZ: SQL INJECTION

{% tabs %}
{% tab title="Question" %}
Which of the following approaches is an effective way of protecting yourself against SQL injection?

* [ ] Using parameterized statements in your code.
* [ ] Moving your database to a separate server.
* [ ] Frequently rotating your database passwords.
* [ ] Using HTTPS in your website.
{% endtab %}

{% tab title="Answer" %}
Which of the following approaches is an effective way of protecting yourself against SQL injection?

* [x] Using parameterized statements in your code.

{% hint style="info" %}
**Correct.** Parameterized statements are the single most useful way of protecting your site against injection attacks.
{% endhint %}

* [ ] Moving your database to a separate server.
* [ ] Frequently rotating your database passwords.
* [ ] Using HTTPS in your website.
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Question" %}
**True or False:** Using an Object Relational Mapping tool will make you completely immune to SQL injection attacks.

* [ ] True
* [ ] False
{% endtab %}

{% tab title="Answer" %}
**True or False:** Using an Object Relational Mapping tool will make you completely immune to SQL injection attacks.

* [ ] True
* [x] False

{% hint style="info" %}
**Correct.** Most ORM tools allow you to construct queries, so you still need to be wary of injection vulnerabilities.
{% endhint %}
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Question" %}
**True or False:** SQL Injection attacks always involve the attacker sending an unexpected quote character.

* [ ] True
* [ ] False
{% endtab %}

{% tab title="Answer" %}
**True or False:** SQL Injection attacks always involve the attacker sending an unexpected quote character.

* [ ] True
* [x] False

{% hint style="info" %}
**Correct.** SQL statements that query NUMBER fields don’t typically use quote characters, and can still be vulnerable to injection attacks.
{% endhint %}
{% endtab %}
{% endtabs %}
