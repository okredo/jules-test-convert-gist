# Detailed Learnings by Year

This file contains a detailed breakdown of technical notes, snippets, and learnings, organized by year and quarter.

---

## 2024
1. dev llm-based apps and deployments many things
2. docker with aws ecr
3. ml ops many things
4. back to sql...?! ;-)
5. back to python...?! ;-)
6. `tr -d '\n' < input.txt > output.txt`
7. `https://us-west-2.console.aws.amazon.com/cloudwatch/home?region=us-west-2#metricsV2?graph=~(view~'timeSeries~stacked~false~start~'-PT24H~end~'P0D~region~'us-west-2~metrics~(~(~'AWS*2fBedrock~'InvocationThrottles~'ModelId~'anthropic.claude-3-sonnet-20240229-v1*3a0)))&query=~'*7bAWS*2fBedrock*2cModelId*7d`

---

## 2023
1. gpt things
2. parallels (gnu)
3. back to java...?! ;-)
4. [Proxies in JavaScript are widely used in various scenarios where you need to customize or intercept operations performed on objects.](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/API/proxy)
5. https://developer.hashicorp.com/terraform/cli/commands/console

---

## 2022
1. UV_THREADPOOL_SIZE equal to num cores
2. `Intl.DateTimeFormat`
3. [How to fix this:](https://github.com/aws-samples/eb-node-express-sample/issues/18)Invalid option specification (Namespace: 'aws:elasticbeanstalk:container:nodejs:staticfiles', OptionName: '/static'): Unknown configuration setting.
4. https://holub.com/heuristics/
5. https://developer.mozilla.org/en-US/docs/Web/CSS/At-rule
6. https://davidwalsh.name/logpoints https://davidwalsh.name/monitorevents !!
7. and [logpoints](https://davidwalsh.name/logpoints) !!
8. `git push origin my-branch --force` can be done thus: `git push origin +my-branch` !!
9. CSS `:out-of-range`
10. https://github.com/ossf/package-manager-best-practices/blob/main/published/npm.md#npm-best-practices-guide
11. form input value type functions, e.g., `.numberValue` and `.dateValue` to get the real types from the form strings !!
12. `:global(svg.{classname})` turn on css to affect svg enclosed in `imported` rule:
```
<style lang="postcss">
  :global(svg.imported) {
    @apply h-2 m-2;
    @apply sm:h-4;
  }
</style>
```
13. Terraform will initialise any state configuration before any other actions such as a plan or apply. Thus you can't have the creation of the S3 bucket for your state to be stored in be defined at the same time as you defining the state backend. Terraform also won't create an S3 bucket for you to put your state in, you must create this ahead of time. You can either do this outside of Terraform such as with the AWS CLI (https://stackoverflow.com/a/52381280/310382)

---

## 2021

### Q4 2021
1. scrolling in react to effect [lazy loading](https://thewebdev.info/2021/03/16/how-to-update-a-state-in-a-react-component-in-a-scroll-event-listener) from constrained origin api
2. `curl -w "Connect time: %{time_connect} Time to first byte: %{time_starttransfer} Total time: %{time_total} \n" -o /dev/null https://www.example.com/yourobject`
3. aws API Gateway: adding default TTL (cache) to routes in a distribution
4. Aws: setting up an EC2 instance w ssh term access. `aws lambda get-function --function-name MY_FUNCTION_NAME --query 'Configuration.[State, LastUpdateStatus]’
5. `/Person|progs|~Descriptors/` in chrome inspector’s network filter is way to do regex
6. `aws lambda get-function --function-name 31ulznw-70k3bga --query 'Configuration.[State, LastUpdateStatus]' --profile {profile} --region us-east-1`
```
[
    "Active",
    "Successful"
]
```
7.  serverless --component="@sls-next/serverless-component@1.17.0" removed this to fix serverless*.yml

### Q3 2021
1. dynamodb rest api limits
2. MemSize and TimeOut... adjust SAM template to set these in lambda
3. using SAM template to create dynamodb rest interface on AWS using api gateway, lambda for the dynamo db -> rest apis & db !!!
4. using VS CODE!
5. Using http://api.marketstack.com/v1/tickers/CLS.XJSE/eod?access_key=e4166fae076a9c33ad8a939f154727af and http://api.currencylayer.com/live?access_key=563d0056ce00a01ee61d6acfd0d9f5c3&currencies=USD,ZAR,CAD,PLN,MXN&format=1n to get stock and forex data and publish in a lambda using 2 async await GET calls combined and w some computation deployed to end-pt using SAM and VSCODE
6. Promise.all( PUT transactions to save data to DynamoDB )
7. Async await Jack H ===> use as a cache (Promise is cached).
8. Sigmoid functions for classification via NNs.
9. Promise-Pool for async fetch processing using concurrency.
10. DayJS for locale-enabled ADD() functions for Program Times data.
11. cache settings in distribution seem to help w cloudfront cache hits??!!
12. reset cache on a path: aws cloudfront create-invalidation --distribution-id distribution_ID --paths "/*"
13. SWR !! Custom hooks!
14. invalidation of cloudfront cache via cmd line or console `curl -w "Connect time: %{time_connect} Time to first byte: %{time_starttransfer} Total time: %{time_total} \n" -o /dev/null https://{domain.com}/api/GetItem/184854`
15. maybe need to learn to do this: https://medium.com/today-i-solved/how-to-deploy-next-js-on-aws-ec2-with-ssl-https-7980ec6fe8d3
16. got the serverless lambda generic running and deploying to CFront. `aws sts decode-authorization-message --encoded-message "above message" --profile "" --region "region"`

### Q2 2021
1. Inheriting via CSS, Selector tutorial: https://lea.verou.me/?ck_subscriber_id=478681662
2. added a delay using hooks https://stackoverflow.com/a/59417556/310382
3. Array.isArray(arr) not typeof, for arrays…. !!! https://www.eventbox.dev/published/lesson/innovator-island/1-deploy/1-overview.html
4. Cloud9 IDE, git integration on aws, etc.
5. Hashicorp registry docs…”attribute references”/implicit references…
6. what you need to refer to re a declared resource that was dynamically created. https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/security_group#attributes-reference e.g., if you want the public ip of the newly created ec2 instance, see aws_instances/resource/attributes-ref/public_ip: “aws_instance.example.public_ip
7. Cognito setup at https://dashboard.uum.gravitymobile.com/user Uses aws/cognito console to create ID Pools, User Pools, for dev/stage/prod
8. in app: aws-amplify.json config files

### Q1 2021
1. "bastion host": AWS related definition is that bastion hosts are "instances that sit within your public subnet and are typically accessed using SSH or RDP. Once remote connectivity has been established with the bastion host, it then acts as a ‘jump’ server, allowing you to use SSH or RDP to log in to other instances (within private subnets) deeper within your VPC. When properly configured through the use of security groups and Network ACLs (NACLs), the bastion essentially acts as a bridge to your private instances via the internet.  e.g., we use API gw for this.
2. dynamo db: A read capacity unit represents one strongly consistent read per second, or two eventually consistent reads per second, for an item up to 4 KB in size.
3. proper mui theming:
```javascript
const materialTheme = createMuiTheme({
  overrides: {
    MuiDialogPaper: {
      backgroundColor: "white",
    },
    MuiInput: {
      root: {
        color: "white",
      },
    },
  },
});
 <ThemeProvider theme={materialTheme}>
      <DatePicker
        className={classes.onNow}
        value={selectedDate}
        onChange={() => handleChange(selectedDate)}
      />
    </ThemeProvider>
  ```
4. https://d1.awsstatic.com/training-and-certification/docs-sa-assoc/AWS-Certified-Solutions-Architect-Associate_Sample-Questions.pdf
5. https://d1.awsstatic.com/training-and-certification/docs-dev-associate/AWS-Certified-Developer-Associate_Sample-Questions.pdf
6. `git st -uno -` don’t bother to show untracked files
7. Js has streams - https://web.dev/streams/ e.g. for piping an HTTP response stream through a transform stream that decodes bytes into bitmap data, and then through another transform stream that translates bitmaps into PNGs.
8. react/plain JS: use actual branching syntax not && to render conditionally
It actually seems counter-intuitive because we often use && in an if condition to say: if both of these values are truthy, then do this thing, otherwise don't.
Unfortunately for our use-case, the && operator also has this "feature" where if both values aren't truthy, it returns the value of the falsy one
don’t do this:
```javascript
{contacts.length &&
6          contacts.map(contact => (
7            <li key={contact.id}>
8              {contact.firstName} {contact.lastName}
9            </li>
10          ))}
```
do this:
```javascript
{contacts.length
6          ? contacts.map(contact => (
7              <li key={contact.id}>
8                {contact.firstName} {contact.lastName}
9              </li>
10            ))
11          : null}
```
9. ESClient put/delete/get alias functions - use of ES node client.
10. in a bash script: $$ ===> is the PID of the shell/task.
11. undefined vs null https://2ality.com/2021/01/undefined-null-revisited.html
12. styled components the right way? https://www.joshwcomeau.com/css/styled-components
13. use filter to remove empty array elems: https://stackoverflow.com/questions/44602661/javascript-lodash-how-to-remove-empty-arrays
14. Lambda function env vars are encrypted! - how to decrypt if using console to encrypt?
15. can use for keys etc
16. Vibrant.js for picking up colors from image
17. padding-top: 100% and width:100% in css gives you a perfect square. (width and height of its container being square too, that is)
18. ES: combine range query with match phrase (You need to do it like using a bool/must query)
19. ES: _update_by_query for a single field
```json
POST /hosts/_update_by_query
{
  "script": {
    "inline": "ctx._source.sort = '5'",
    "lang": "painless"
  },
  "query": {
    "match": {
      "_id" : "114683"
    }
  }
}
```
20. ES Aggs to make a histogram:
 ```json
 "aggs": {
    "datesplitfoo": {
      "date_histogram": {
        "field": "doc.airDate",
        "calendar_interval": "month"
      }
    }
  }
```
ES date range:
```json
{
  "aggs": {
    "range": {
      "date_range": {
        "field": "date",
        "format": "MM-yyyy",
        "ranges": [
          { "to": "now-10M/M" },
          { "from": "now-10M/M" }
        ]
      }
    }
  }
}
```
21. JS Testing Summit:
https://testing-playground.com/
https://testing-library.com
22. Cypress intercept API
23. datadog for real world performance test in prod dashboards etc.
24. Launch Darkly. Feature flags on releases.
25. Talia Nassi YouTube talk
26. creating a new policy in IAM for KMS. This Policy has to be the attached to the Role that supports the Service. I added this policy to my lambda_role. this allowed my lambda to process encrypted env vars. Yay.
27. `DELETE /my-index-000001/_alias/alias1. PUT /my-index-000001/_alias/alias1`
28. terraform import usage to pull down console created resources on aws, e.g., a lambda: https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/lambda_permission
29. Ability to configure existing VPC in a new tf lambda definition:
```terraform
vpc_config {
    subnet_ids         = ["subnet-07e4e50c31b311334", "subnet-0f50100f6b3422ac2"]
    security_group_ids = ["sg-fc97deecc8f719b9"]
    # vpc_id                 = "vpc-0c7e5f7f74c6a88a3"
  }
```
30. Ability to zip AWS Lambda function on the fly (terraform)
```terraform
data "archive_file" "lambda_zip" {
  type        = "zip"
  source_dir  = "../../post-catalog-ingestion"
  output_path = "../post-catalog-ingestion.zip"
}
resource "aws_lambda_function" "post-catalog-ingestion" {
  # (resource arguments)
  filename         = "../post-catalog-ingestion.zip"
  source_code_hash = data.archive_file.lambda_zip.output_base64sha256
  function_name    = "post-catalog-ingestion"
  handler          = "index.handler"
  role             = "arn:aws:iam::158448406516:role/service-role/catalog-ingestion-tool-role-h3qcoq4k"
  timeout          = "30"
  runtime          = "nodejs12.x"
  tags = {
    "Email"       = "ShowcaseDev@nielsen.com"
    "Environment" = "dev",
    "Product"     = "GlobalSportsData",
    "Role"        = "Streaming Sports Catalog Product Demo",
    "Stack"       = "VideoShowcaseDataServices-dev",
    "Vertical"    = "Video"
  }
}
```
31. Tf full intro video course - modules, variables, intro to HCL.
32. Blockchain management in React.typescript using MobX for state - video course
33. create and manage a pod in Kubernetes using oreilly runtime env.
34. basic kubectl command for creating and interacting with Pods

---

## 2020

### Q4 2020
1. ssh-keygen
2. in .ssh folder create file called ‘config’.
3. docker start | stop | rem to manage images
4. managed a minecraft jar.
5. Learn how to loop in useEffect (array of promises in query? order etc)
6. Learn how to pass css className through to subcomponent in MaterialReact.
7. Use loop in one useEffect to -ahem- effect the promise chain in another useEffect in same component.
8. svg text experimental settings:
```xml
<svg viewBox="0 0 140 40" xmlns="http://www.w3.org/2000/svg">
<text y="15" text-rendering="geometricPrecision">Geometric precision</text>
<text y="35" text-rendering="optimizeLegibility">Optimized legibility</text>
</svg>
```
9. amplify amin UI new in AWS amplify. (https://virtual.awsevents.com/media/1_2icq0o0c)
10. REM is always relative to the font-size of the base font of the site; EM is relative to font-size of parent element.
11. Also VW for font is problematic if you use ctrl+/-

### Q3 2020
1. AWS solution arch associate cert training
2. Add testing to a react project and test ajax, UI and ajax w mocks
3. UI: How to scale svg viewport contents
4. UI: use css to match
5. Shadow DOM: parts pseudo class; To summarize, parts allow web component developers to allow consumers to style certain key elements inside a Shadow DOM. We saw it can be done statically by setting a part value beforehand as well as dynamically by adding and removing values from the part's attribute string. (https://egghead.io/lessons/javascript-enabling-css-manipulation-inside-the-shadow-dom-using-the-part-pseudo-class?pl=web-components-f902)
6. Shadow DOM refers to the ability of the browser to include a subtree of DOM elements into the rendering of a document, but not into the main document DOM tree.

### Q2 2020
1. Deploying video assets (visual merchandise)
2. generating raw SVG via react components
3. svg pointer events via `<set>` tag…!
4. centering svg text via dy attire.
5. box-shadow ‘inset’ attribute
6. ES: how do you know how many shards/index? => depends on your system reqs.
7. ES: match queries vs term queries
8. Effective vs effective (lower case also used in Match because uses Analyzer, whereas Term just uses inverted index… where only Upper Case (Effective Java. Title search)
9. when do you NOT need analysis? Bools, dates, other term-filtered, range queries etc.
10. "explain": true => provide inline info re the results.
11. “fuzziness” : 1 => allows for e.g., spelling mistakes but only one level of char off. e.g., Computer Sci vs “Compuuter Sci” still works but “Compuuuter" won’t.
12. NLSN From Witness to Advocate Div training course.

### Q1 2020
1. `jq variables (.[] | .tmsId as $id | {ekp_curate: [ .ads.ekp[] | { key:.category, value:[ {"kw":(.keywords | to_entries[].value.tag), "progs":[$id]} ] } ] | from_entries} )`
2. Setup Google Analytics to track your React.js website
3. Variables in package.json
4. In JS: while both function declarations and variable declarations are hoisted, function declarations are hoisted first and then variables. Duplicate var declarations (but not assignments!) are also ignored. (https://quiz.typeofnan.dev/hoisting-race-to-the-top/)
5. Apigee administration https://apigee.com/platform/orenkredo-eval/proxies/celeb-xml-apigee-test/overview/1
6. Rust
7. js equality dan a blog.
8. Android service using retrofit api to query AOD API.
9. aws saml set up micro account
10. aws cli set up s3 bucket; cloud front cdn; uses certificate
11. Serves non-public binary asset via Cloud Front.
12. bash passing variables, functions - see aws cli scripts above
13. AWS SAM / CLOUDFRONT TEMPLATES

---

## 2019

### Q4 2019
1. browser facilitated image lazy loading to handle the volume of images returned with the search results.
AWS Loft:
2. layers of aws ai … see photo.
3. sassy alexa youtube clip
4. predicting time series forecasts
5. personalization
6. try personalization for recommendations
7. AWS Re:Invent - 7 sessions
8. RxJS egghead free class
9. suspense egghead paid class
10. Fixed position floating “Mood for Something Else” button
11. image preloading per Kent Dodds egghead vid using index.html
12. vs image prefetching which gets rid of the warning and is not same as already in cache, but fast enough (pre-cache!)
13. `const query = window.matchMedia((max-width: ${breakpoints["desktopLg"]}px));` for internal to JS media queries.
14. responsive images w srcSet/srcset but use size not density maybe to fix that flaky 0x0 rendering issue?
15. SVG `currentColor` function: `fill="currentColor”` uses outer div color - no need for component just to pass style.
16. Shadow DOM: `attachShadow();` part of Web Components; e.g., audio controls not in main DOM.
17. built create-react-app from scratch!
18. Svelte
19. basic elastic search o reilly class

### Q3 2019
1. api gateway testing a lambda
2. Publishing a Message to an SNS Topic via lambda
3. Using Packages and Native nodejs Modules in AWS Lambda
4. Using CloudWatch to Monitor your AWS Lambda and send Alerts on Errors
5. es client Bulk API
6. React Hooks useState, useReducer, useMemo, useCallback, useEffect
7. implementing responsive images (different images in HTML for different situations) and all you are doing is switching between different versions of the same image (the vast majority of usage), all you need is the srcset attribute on the `<img>` (https://css-tricks.com/responsive-images-youre-just-changing-resolutions-use-srcset/)
8. Added lambda rule Cloudwatch event to run at 4pm GMT mon-fri (via aws console)
9. `git rev-parse --show-cdup`
10. how to add a (added genre) field to an index, based on onConnect lookups of tmsIDs
11. how to do async, looped async within effect hook (react)

### Q2 2019
1. box model outer relative inner absolute e.g. search icon
2. pseudo tags after and before w the image background from game stars
3. i18N via css via data and pseudo tags
4. FBT
5. Machine Learning: pyTorch
6. React devtools / console… esp r$
7. Chrome devs: Build performant and progressive React applications.
8. F8 React Hooks and Intro to AI for Devs videos; introducing-pytorch-10
9. SVG tutorial from emails by Fullstack.
10. SVG: Chris Coyier video (10 things you should do w SVG)
11. SVG 6 steps to draw something email video & code from Fullstack
12. google/io video: V8 Engine: new JS features: `ObjectEntries()` and `ObjectFromEntries()`
13. `const TheGlobalThis = globalThis`
14. should not need this, really, unless building a library
15. `Array.sort()` is now stable(!)
16. `Promise.any()` and `Promise.allSettled()`
17. new WeakRef() proposal for current Map() memleak…
18. WebAssembly for Web Developers (googleIO vid)
19. tail-call-optimization
20. Design tutorial re charts in D3.js from FullStack
21. amplify command line egghead tutorial (wed,thu,fri)
22. Native lazy loading in new Chrome
23. Shadow DOM
24. CAP Theorem
25. pseudo elements (e.g., :before)
26. xmllint to parse xml from command line
27. ES - create and update indices via JS client