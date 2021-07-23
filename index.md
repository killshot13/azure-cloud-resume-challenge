# Cloud Resume Challenge

## Microsoft Azure Version

_Inspired by the [original Cloud Resume Challenge blog post](https://forrestbrazeal.com/2020/04/23/the-cloud-resume-challenge/) which was the brainchild of [Forrest Brazael](http://forrestbrazeal.com/)_

### Updated for 2021

**Instructions:**
Follow steps 1-16 as listed below, in order, without skipping any stages or choosing to dabble only with the sections that seem most fun or interesting.

Why? Because after completing the Cloud Resume Challenge from start to finish, you will already have more useful skills than a lot of people who graduate from university computer science programs.

More specifically, you will understand something about full-stack software development, version control, infrastructure as code, automation, continuous integration and delivery, cloud services and “serverless”, application security, and networking.

Most importantly, you will have demonstrated the number-one skill in a cloud engineer’s toolbox: the ability to learn fast and Google new terminology with precision.

And you’ll have learned by doing, because the instructions aren't specific enough to figure anything out without going down some dark, lengthy rabbit holes.

Alternatively, if you give this project a try and realize that you hate it, or you’re just not interested, you’ll have learned a valuable lesson about whether a career in the cloud is truly for you – because these are the types of problems that real cloud engineers and developers really work on every day.

🥳 GOOD LUCK! 🥳

#### 1. Certification

Ideally, your resume should already have the [Microsoft Azure AZ-900](https://docs.microsoft.com/en-us/learn/certifications/exams/az-900) certification on it. If not, then you should pursue this certification straightaway after completing this challenge.

Microsoft Azure AZ-900 is an introductory certification that orients you on the industry-leading Azure cloud – if you have a more advanced Azure cert, that’s fine too. No cheating: include the validation code on the resume. You can sit this exam online for $100 USD. [Cloud Academy](https://cloudacademy.com/learning-paths/az-900-exam-preparation-microsoft-azure-fundamentals-524) offers exam prep resources.

#### 2. HTML

Your resume needs to be written in [HTML](https://developer.mozilla.org/en-US/docs/Web/HTML). Not a Word doc, not a PDF. Here is [an example](https://codepen.io/emzarts/pen/OXzmym) to get you started.

#### 3. CSS

Your resume needs to be styled with [CSS](https://www.w3schools.com/css/). No worries if you’re not a designer – just make it clean and simple. It doesn’t have to be fancy. But we need to see something other than raw HTML when we open the webpage.

#### 4. Static Azure Storage Website

Your HTML resume should be deployed online as an [Azure Storage static website](https://docs.microsoft.com/en-us/azure/storage/blobs/storage-blob-static-website). Services like Netlify and GitHub Pages are great and I would normally recommend them for personal static site deployments, but they are a bit simple for a real-world cloud-based environment. Use Azure Storage.

#### 5. HTTPS

The Azure Storage website URL should use [HTTPS](https://www.cloudflare.com/learning/ssl/what-is-https/) for security. You will need to use the Azure [Content Delivery Network](https://docs.microsoft.com/en-us/azure/cdn/cdn-overview) (CDN) to help with this.

#### 6. DNS

Point a custom DNS domain name to the Azure CDN distribution, so your resume can be accessed at something like my-personal-brand.com. You can use [Azure Portal](https://portal.azure.com/) or any other DNS provider for this. A domain name usually costs about ten bucks to register.

#### 7. Javascript

Your resume webpage should include a visitor counter that displays how many people have accessed the site. You will need to write a bit of [Javascript](https://developer.mozilla.org/en-US/docs/Web/JavaScript) to make this happen. Here is a [helpful tutorial](https://www.codecademy.com/learn/introduction-to-javascript) to get you started in the right direction.

#### 8. Database

The visitor counter will need to retrieve and update its count in a database somewhere. I suggest you use [Azure’s CosmosDB](https://docs.microsoft.com/en-us/azure/cosmos-db/) for this. (Use on-demand pricing for the database and you’ll pay essentially nothing, unless you store or retrieve much more data than this project requires.) Here is a [great free course](https://www.classcentral.com/course/microsoft-azure-cosmos-db-43815) on CosmosDB.

#### 9. API

Do not communicate directly with CosmosDB from your Javascript code. Instead, you will need to create an [API](https://medium.com/@perrysetgo/what-exactly-is-an-api-69f36968a41f) that accepts requests from your web app and communicates with the database. I suggest using [Azure API Management](https://azure.microsoft.com/en-us/services/api-management/) and [Azure Functions](https://docs.microsoft.com/en-us/azure/azure-functions/) for this. Both services will be free or close to free for what we are doing.

#### 10. Python

You will need to write a bit of code in the Azure function; you could use more Javascript, but it would be better for our purposes to explore Python – a common language used in back-end programs and scripts – and its [Azure SDK](https://azure.github.io/azure-sdk-for-python/). Here is a good, free [Python tutorial](https://www.learnpython.org/).

#### 11. Tests

You should also include some tests for your Python code. Here are [some resources](https://realpython.com/python-testing/) on writing good Python tests.

#### 12. Infrastructure as Code

You should not be configuring your API resources – the CosmosDB table, the API Management, the Azure function – manually, by clicking around in the Azure console. Instead, define them in an [Azure Serverless Application Management (SAM) template](https://docs.microsoft.com/en-us/azure/logic-apps/create-serverless-apps-visual-studio) and deploy them using [Visual Studio](https://visualstudio.microsoft.com/) and the [Azure CLI](https://docs.microsoft.com/en-us/cli/azure/use-cli-effectively). This is called “[infrastructure as code](https://www.hashicorp.com/resources/what-is-infrastructure-as-code)” or IaC. It saves you time in the long run.

#### 13. Source Control

You do not want to be updating either your back-end API or your front-end website by making calls from your laptop, though. You want them to update automatically whenever you make a change to the code. (This is called [continuous integration and deployment](https://docs.github.com/en/actions/guides/about-continuous-integration), or CI/CD.) Create a private [GitHub repository](https://docs.github.com/en/github/creating-cloning-and-archiving-repositories/creating-a-repository-on-github/creating-a-new-repository) for your backend code.

#### 14. CI/CD (Back end)

Set up [GitHub Actions](https://help.github.com/en/actions/getting-started-with-github-actions/about-github-actions) such that when you push an update to your Serverless Application Model template or Python code, your Python tests get run. If the tests pass, the Azure SAM application should get packaged and deployed to Microsoft Azure.

#### 15. CI/CD (Front end)

Create a second private GitHub repository for your website code. Create GitHub Actions such that when you push new website code, your [Azure Blob Storage](https://docs.microsoft.com/en-us/azure/storage/common/storage-introduction#blob-storage) automatically gets updated. (You may need to configure [Blob Storage](https://docs.microsoft.com/en-us/azure/storage/blobs/) service to [effectively set your Cache-Control headers](https://docs.microsoft.com/en-us/azure/cdn/cdn-manage-expiration-of-blob-content).) Important note: _DO NOT commit Azure credentials to source control! Bad hats will find them and use them against you!_

#### 16. Blog Post

Finally, in the text of your resume, you should link a short blog post describing some things you learned while working on this project. [DEV Community](https://dev.to/) is a great place to publish if you don’t have your own blog.

---

**CREDITS:**
For more background, you can read the [original Cloud Resume Challenge blog post](https://forrestbrazeal.com/2020/04/23/the-cloud-resume-challenge/) which was the brainchild of [Forrest Brazael](http://forrestbrazeal.com/).
