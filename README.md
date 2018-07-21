# Usage
#### First, get your anticaptcha API key.
Go to your [Anticaptcha API setup panel](https://anti-captcha.com/clients/settings/apisetup) and copy your **Account key**.

#### Add library to your project:
``` powershell
PM> Install-Package AnticaptchaNet
```

#### And simply:
```cs
Anticaptcha anticaptcha = new Anticaptcha("YOUR_ANTICAPTCHA_KEY");

if (anticaptcha.Balance < 0.1) return;

int taskId = anticaptcha.CreateTask("captcha_filepath.jpg");

TaskResult taskResult = anticaptcha.GetTaskResult(taskId);

while (!taskResult.IsDone)
{
    Thread.Sleep(1000); // Wait for captcha solution.
    taskResult = anticaptcha.GetTaskResult(taskId);
}

string captchaSolution = ((Captcha.ImageToTextSolution)taskResult.Solution).Text;
```

## Dependencies
- [Newtonsoft.Json](https://www.newtonsoft.com/)
 

# Contribution
**Feel free to help us with something from this list!**
## TODO:
####  Every task type:
- [x] **Image captchas**: (ImageToTextTask.cs)
- [ ] **Google NoCaptcha with proxy**: (NoCaptchaTask.cs)
- [ ] **Google NoCaptcha without proxy**: (NoCaptchaTaskProxyless.cs)
- [ ] **FunCaptcha with proxy**: (FunCaptchaTask.cs)
- [ ] **FunCaptcha without proxy**: (FunCaptchaTaskProxyless.cs)
- [ ] **Select objects on a gridded image**: (SquareNetTask.cs)
- [ ] **Custom captcha task with arbitrary form inputs**: (CustomCaptchaTask.cs)
- [ ] **Sliding captcha GeeTest with proxy**: (GeeTestTask.cs)
- [ ] **Sliding captcha GeeTest without proxy**: (GeeTestTaskProxyless.cs)
     
#### 2. Summary for every field and method in the library.
#### 3. Documentation.
#### 4. More examples.

## If you have any questions
Feel free to write me in [Telegram](https://t.me/sheefoo25).
<3