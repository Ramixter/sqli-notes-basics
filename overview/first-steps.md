# First Steps

This is the vulnerable application we will be trying to hack with a <mark style="color:red;">**SQL INJECTION**</mark> attack.

<figure><img src="../.gitbook/assets/Window-000132.png" alt=""><figcaption></figcaption></figure>

Here are the application logs. Watch what happens here when you interact with the vulnerable application.

<figure><img src="../.gitbook/assets/Window-000135.png" alt=""><figcaption></figcaption></figure>

Go ahead and try logging in with the following credentials:\
&#x20;\- Email: `user@email.com`\
&#x20;\- Password: `password`

<figure><img src="../.gitbook/assets/Window-000136.png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/Window-000137.png" alt=""><figcaption></figcaption></figure>

Okay, so guessing the password didn't work. Let's try adding a quote character after the password:\
&#x20;\- Email: `user@email.com`\
&#x20;\- Password: `password'`

<figure><img src="../.gitbook/assets/Window-000138 (1).png" alt=""><figcaption></figcaption></figure>

Hmmm. The application crashed with an unexpected error. What could that mean?

<figure><img src="../.gitbook/assets/Window-000139 (1).png" alt=""><figcaption></figcaption></figure>

The logs show a SQL syntax error. This indicates that the quote character messed something up in an unexpected way.

This is what the application code looks like behind the scenes.

{% tabs %}
{% tab title="Empty" %}
<figure><img src="../.gitbook/assets/Window-000141.png" alt=""><figcaption></figcaption></figure>
{% endtab %}

{% tab title="Password" %}
<figure><img src="../.gitbook/assets/Window-000142 (1).png" alt=""><figcaption></figcaption></figure>
{% endtab %}

{% tab title="Password'" %}
<figure><img src="../.gitbook/assets/Window-000143.png" alt=""><figcaption></figcaption></figure>
{% endtab %}
{% endtabs %}

Enter the password `password'` and watch the code window.

The quote is inserted directly into the SQL string and terminates the query early. this is what caused the syntax error we saw in the logs.

This behavior indicates that the application might be vulnerable to <mark style="color:red;">SQL INJECTION</mark>.

Enter the following credentials and click "Log in":\
&#x20;\- Email: `user@email.com`\
&#x20;\- Password: `' or 1=1--`

<figure><img src="../.gitbook/assets/Window-000144.png" alt=""><figcaption></figcaption></figure>

And we are in! We successfully gained acces to the application without having to guess the password using <mark style="color:red;">SQL INJECTION</mark>.

<figure><img src="../.gitbook/assets/Window-000145.png" alt=""><figcaption></figcaption></figure>

The -- characters you entered caused the database to ignote the rest of the SQL statement, allowing you to be authenticated without having to supply thre real password.

<figure><img src="../.gitbook/assets/Window-000146.png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
Phew. Now we know how <mark style="color:red;">SQL INJECTION</mark> works, let's learn how to protect against this kind of attack.
{% endhint %}
