# First Test Automation
npx Codeceptjs run
```
Feature('login');

Scenario('Yanlış kullanıcı adı @testcase1', ({ I }) => { 
    I.amOnPage('https://amazon.com');
    I.waitForElement('//div[@id="nav-signin-tooltip"]');
    I.click('//div[@id="nav-signin-tooltip"]');
    I.waitForElement('//input[@id="ap_email');
    I.fillField('//input[@id="ap_email"]','yanlis_mail_yaz');
    I.waitForElement('//input[@id="continue"]');
    I.click('//input[@id="continue"]');
    I.seeElement('//*[contains(text(),"cannot find")]');
});

Scenario('Doğru kullanıcı adı, yanlış şifre @testcase2', ({ I }) => {
    I.amOnPage('https://www.amazon.com');
    I.waitForElement('//div[@id="nav-signin-tooltip"]');
    I.click('//div[@id="nav-signin-tooltip"]');
    I.fillField('//input[@id="ap_email"]','dogru_mail_yaz');
    I.waitForElement('//input[@id="continue"]');
    I.click('//input[@id="continue"]');
    I.waitForElement('//input[@id="ap_password"]');
    I.click('//input[@id="ap_password"]');
    I.fillField('//input[@id="ap_password"]','yanlis_sifre_yaz');
    I.waitForElement('//input[@id="signInSubmit"]');
    I.click('//input[@id="signInSubmit"]');
    I.seeElement('//*[contains(text(),"Important Message")]');
});

Scenario('Doğru kullanıcı adı, doğru şifre @testcase3', ({ I }) => {
    I.amOnPage('https://www.amazon.com');
    I.waitForElement('//div[@id="nav-signin-tooltip"]');
    I.click('//div[@id="nav-signin-tooltip"]');
    I.fillField('//input[@id="ap_email"]','dogru_mail_yaz');
    I.waitForElement('//input[@id="continue"]');
    I.click('//input[@id="continue"]');
    I.waitForElement('//input[@id="ap_password"]');
    I.click('//input[@id="ap_password"]');
    I.fillField('//input[@id="ap_password"]','dogru_sifre_yaz');
    I.waitForElement('//input[@id="signInSubmit"]');
    I.click('//input[@id="signInSubmit"]');
    I.seeElement('//*[contains(text(),"Hello,")]');
});
```
