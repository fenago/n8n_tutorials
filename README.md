# n8n_tutorials

# n8n Foundations Tutorial: Workflows, Variables, and JSON

## Getting Started with n8n

### Creating Your Account

1. **Navigate to n8n's website** using the provided link
2. **Click "Sign up for a free trial"** 
3. **Fill out the registration form:**
   - Enter your name
   - Enter your email address
   - Create a password
   - **Give your account a name** - this will appear in your URL (e.g., `yourname.app.n8n.cloud`)
4. **Click "Start our 14-day free trial"**

### Initial Setup Process

1. **Complete the onboarding questionnaire:**
   - Select your team type (e.g., "Product and Design")
   - Choose your company size
   - Select your comfort level with technical tasks
   - Choose how you heard about n8n (e.g., "YouTube")
2. **Click "Submit"**
3. **Skip inviting team members** for now (you can do this later)
4. **Click "Start Automating"**

## Understanding the n8n Dashboard

### Dashboard Overview

When you first enter n8n, you'll see:

- **Top left corner:** Shows **14 days left** in your free trial and **0 out of 5,000 executions used**
  - An **execution** = one complete workflow run from start to finish
- **Left sidebar navigation:**
  - **Overview** - main dashboard
  - **Personal** - your personal projects
  - **Shared with me** - collaborative projects
  - **Add project** - create new project folders
  - **Admin panel** - upgrade settings and billing

### Exploring the Admin Panel

1. **Click on the admin panel** in the left sidebar
2. Here you can see:
   - **Execution count**
   - **Active workflows count**
   - **Version management**
   - **Billing and upgrade options**
3. **Click "Open"** to return to your workspace

## Your First AI Agent Demo

### Testing the Sample AI Agent

1. **Click "Test a simple AI agent example"** on the dashboard
2. **Click "Open Chat"** at the bottom of the workflow
3. **Type "hi"** in the chat box
4. **Notice the error** - the workflow fails because there are no credentials set up

### Setting Up OpenAI Credentials

1. **Click on the red error node** to see the error details
2. **Read the error:** "Error in subnode OpenAI model"
3. **Click on the OpenAI model node** (the red node)
4. **Click "Claim Credits"** to use n8n's free OpenAI credits (100 free credits)
5. **Click the "Repost Message" button** to resend your "hi" message
6. **Watch the AI respond** with instructions about adding memory

### Adding Memory to Your Agent

1. **Click the plus button** under the "Memory" section of the agent
2. **Select "Simple Memory"**
3. **Type "done"** in the chat to confirm
4. **Watch the AI respond** using its new memory capability
5. **Click "Save"** in the top right corner to save your progress
6. **Click "Overview"** to return to the main dashboard

## Creating Your First Workflow

### Setting Up a New Workflow

1. **Click "Create Workflow"** in the top right corner
2. **Name your workflow** by clicking in the top left field and typing "Demo"
3. **Notice the workflow organization options:**
   - **Projects:** Save workflows in different project folders
   - **Tags:** Organize workflows by categories (customer support, marketing, etc.)

### Understanding Triggers

**Every workflow must start with a trigger** - this determines when your workflow runs.

1. **Click "Add First Step"**
2. **Review trigger options:**
   - **Manual trigger** - run by clicking a button
   - **Event triggers** - new Telegram message, new CRM row, etc.
   - **Schedule triggers** - run at specific times (6 AM daily, etc.)
   - **Webhook triggers** - triggered by external API calls
   - **Form submissions**
   - **Chat messages**

3. **Select "Trigger Manually"** for this example
4. **Click "Test Workflow"** to see how the manual trigger works

### Adding Nodes to Your Workflow

#### Understanding Node Types

After your trigger, you can add different types of nodes:
- **Action nodes** - perform specific tasks
- **Data transformation nodes** - modify data
- **AI nodes** - interact with AI services
- **App integration nodes** - connect to external services

#### Adding an App Integration Node

1. **Click the plus button** after your trigger node
2. **Click "Take action within an app"**
3. **Browse the integrations** - you'll see hundreds of native integrations
4. **Click on "Google Drive"** as an example
5. **Review the available actions:**
   - Copy a file
   - Share a file
   - Create a shared drive
   - And many more natural language options

**Important:** Every app integration requires **credentials** (passwords/API keys) to connect.

#### Adding an AI Node Instead

1. **Delete the Google Drive node** by clicking the delete button
2. **Click the plus button** again
3. **Select "AI"** from the options
4. **Click "OpenAI"**
5. **Select "Message a model"**

### Configuring Your AI Node

#### Understanding Node Structure

Every node has three main sections:
- **Left (Input):** Data coming into this node
- **Middle (Configuration):** Settings and options for this node  
- **Right (Output):** Data produced by this node

#### Setting Up OpenAI Configuration

1. **Configure the resource type:** Select "Text"
2. **Choose the operation:** "Message a model"
3. **Notice the model limitation** with free n8n credits

### Getting Your Own OpenAI API Key

#### Creating an OpenAI API Account

1. **Go to openai.com**
2. **Create an account** (this is different from ChatGPT subscription)
3. **Look for "API Platform Login"** (not ChatGPT login)
4. **Navigate to your dashboard**
5. **Click "API Keys"** in the menu
6. **Click "Create New Key"**
7. **Name your key** (e.g., "n8n Demo")
8. **Copy the secret key**

**Important:** You must add billing information to your OpenAI account for the API key to work.

#### Adding Your API Key to n8n

1. **Return to your n8n workflow**
2. **In the OpenAI node, find the credential section**
3. **Click "Create New Credential"**
4. **Paste your API key**
5. **Name your credential** (e.g., "Demo May 21st")
6. **Save the credential**

### Configuring Your AI Model

1. **Select a model** from the dropdown (e.g., "GPT-4.1 Mini")
2. **In the prompt field, type:** "Tell me a joke"
3. **Click "Test Step"** to run just this node
4. **Review the output** in the right panel

### Understanding Data Views

You can view your data in three different formats:

#### Schema View
- **Most user-friendly**
- **Natural language format**
- **Easy drag-and-drop interface**

#### Table View  
- **Spreadsheet-like format**
- **Good for structured data**
- **Also supports drag-and-drop**

#### JSON View
- **Technical format**
- **Key-value pairs**
- **Universal format understood by all AI models**

### Working with Variables

#### Adding a Set Node

1. **Click the plus button** after your OpenAI node
2. **Select "Data Transformation"**
3. **Choose "Set"** node
4. **Click "Add Field"**
5. **Name the field:** "OpenAI's Response"

#### Using Drag-and-Drop Variables

1. **From the input panel (left side), drag the "content" field**
2. **Drop it into the "Value" field**
3. **Notice the green variable:** `{{ $json.message.content }}`
4. **Click "Test Step"** to see the output

**Key Concept:** Anything in green curly braces `{{ }}` is a **variable** representing dynamic data from previous nodes.

## Understanding JSON

### What is JSON?

**JSON stands for JavaScript Object Notation** - it's a way to structure and identify data.

#### Why JSON Matters:
- **All workflows in n8n are built on JSON**
- **All major AI models understand JSON**
- **When you download templates, they're JSON files**
- **It's universal and standardized**

#### JSON Structure:
- **Key-value pairs:** `"key": "value"`
- **Natural language format:** `"role": "assistant"`
- **Nested structure:** Objects can contain other objects

### Getting Help with JSON

**Pro Tip:** If you ever need help understanding or creating JSON:

1. **Copy any JSON from n8n**
2. **Go to ChatGPT**  
3. **Ask:** "Help me understand this JSON" and paste it
4. **Or ask:** "Convert this natural language to JSON format"

#### Example JSON Creation:
**Input:** "My name is Nate, I'm 23 years old, I went to University of Iowa, I like to play pickleball"

**Output:**
```json
{
  "name": "Nate",
  "age": 23,
  "education": "University of Iowa", 
  "interests": "pickleball"
}
```

### Testing JSON in n8n

1. **Add another Set node**
2. **Instead of manual mapping, select "JSON"**
3. **Paste the JSON from ChatGPT**
4. **Click "Test Step"**
5. **See the structured output** in schema, table, and JSON views

## Creating a Dynamic Chat Workflow

### Switching from Manual to Chat Trigger

1. **Delete your manual trigger**
2. **Add a Chat trigger**
3. **Connect it to your OpenAI node** by dragging the plus sign
4. **Modify your OpenAI prompt:**
   - Delete "Tell me a joke"
   - **Drag the "chatInput" variable** from the input panel
   - **Drop it in the prompt field**

### Testing Your Dynamic Workflow

1. **Save your workflow**
2. **Open the chat**
3. **Type a message:** "My name is Nate, I like to eat ice cream. Make up a funny story about me."
4. **Watch the AI create a personalized response**

The AI will now respond dynamically to any input, just like ChatGPT in your browser.

## Workflow Management Features

### Understanding the Editor

**Top navigation shows "Editor"** - this is where you:
- **Zoom in and out**
- **Move around the canvas**
- **Edit your workflow visually**
- **Workflows flow left-to-right** (like reading)

### Viewing Execution History

1. **Click "Executions"** in the top navigation
2. **See all previous workflow runs**
3. **Click on any execution** to see:
   - **What time it ran**
   - **What data flowed through**
   - **Results from each node**
4. **Click into individual nodes** to see their specific input/output

This is invaluable for debugging and monitoring your automations.

## Importing Templates

### From n8n's Template Library

1. **Go to n8n's website**
2. **Click "Product" → "Templates"**
3. **Browse over 2,100 workflow templates**
4. **Click "Use for Free"** on any template
5. **Choose "Import to Cloud Workspace"**
6. **Set up required credentials**
7. **Click "Continue"**

### From Community Resources

1. **Visit the free School community**
2. **Find "YouTube Resources"**
3. **Download the JSON file** for any workflow
4. **In n8n, create a new workflow**
5. **Click the import button**
6. **Select "Import from File"**
7. **Upload the JSON file**
8. **Follow setup guides** to connect your credentials

## Active vs Inactive Workflows

### Understanding Workflow States

#### Inactive Workflows:
- **Only run when you click "Test Workflow"**
- **Don't execute automatically**
- **Good for testing and development**

#### Active Workflows:
- **Run automatically based on their triggers**
- **Count toward your execution limit**
- **Required for live automations**

### Making a Workflow Active

1. **Your workflow needs a trigger that supports activation:**
   - Schedule triggers
   - Webhook triggers  
   - App event triggers (new HubSpot contact, etc.)
   - **NOT manual triggers**

2. **Add a Schedule trigger example:**
   - Delete your current trigger
   - Add "Schedule" trigger
   - Set it to run "Every day at midnight"
   - **Toggle the "Active" switch** in the top right

3. **Understanding the activation message:**
   - **Executions will run on schedule**
   - **They won't show live in the editor**
   - **You'll see them in the Executions list**

**Critical:** If you want a workflow to run automatically (new contact, daily schedule, etc.), it **MUST be set to Active**.

## Working with Binary Data

### Understanding Binary Data

**Binary data** includes:
- **Images**
- **PDFs** 
- **Word documents**
- **PowerPoint files**
- **Videos**
- **Any non-text files**

### Creating a Form with File Upload

1. **Add a "Form Trigger"**
2. **Configure the form:**
   - **Title:** "Demo"
   - **Description:** "Binary Data"
3. **Add form elements:**
   - **Text field** for "Name" (required)
   - **File field** for "File" (required)
4. **Click "Test Step"** to generate the form

### Testing Binary Data

1. **Fill out the form** with your name
2. **Upload a file** (video, image, document, etc.)
3. **Submit the form**
4. **View the results in n8n:**
   - **Schema/Table/JSON views** show file metadata
   - **Binary view** shows the actual file content
   - **Click "View"** to see/download the actual file

### Working with Binary Data in Workflows

- **Binary data appears as a fourth tab** alongside Schema, Table, and JSON
- **You can reference binary data** in subsequent nodes
- **Many nodes can process binary data** (image recognition, PDF parsing, etc.)
- **Don't be intimidated** - binary is just another data type

## Key Takeaways

### Essential Concepts Mastered:

1. **Workflows** are visual automation sequences
2. **Triggers** determine when workflows run  
3. **Nodes** perform specific actions or transformations
4. **Variables** (green `{{ }}` text) represent dynamic data
5. **JSON** is the universal data format
6. **Executions** track workflow runs
7. **Active vs Inactive** determines automatic execution
8. **Binary data** handles files and media

### Best Practices:

- **Always test nodes individually** before running full workflows
- **Use descriptive names** for workflows and credentials  
- **Organize with projects and tags**
- **Check execution history** for debugging
- **Start with templates** to learn faster
- **Ask AI tools** for help with JSON

### What's Next:

You're now ready to build real automations! The next tutorials will walk you through:
- **Setting up Google integrations**
- **Working with Pinecone vector databases** 
- **Building advanced AI agents**
- **Creating production-ready workflows**

**Remember:** You have **14 days** and **5,000 executions** to practice. By the end of your trial, you'll be comfortable building sophisticated automations that can transform how you work.

# n8n Data Types Tutorial: Understanding String, Number, Boolean, Array, and Object

## Why Data Types Matter

Before building automations and AI agents, it's **crucial to understand data types in n8n**. Data types determine how information is processed, stored, and used in your workflows. Getting this wrong can cause errors and prevent your automations from working properly.

## Setting Up Your Practice Environment

### Creating a Test Workflow

1. **Create a new workflow** in n8n
2. **Add a manual trigger** to start
3. **Add a Set node** after your trigger
   - Click the **plus button** after your manual trigger
   - Select **"Data Transformation"**
   - Choose **"Set"**

The Set node allows you to modify, add, or remove fields - perfect for learning data types.

### Understanding the Set Node Interface

In your Set node, you'll see:
- **Field name input** - what you want to call your data
- **Data type dropdown** - the five types we'll explore
- **Value input** - the actual data content
- **Manual vs Variable options** - fixed values vs dynamic data from previous nodes

**Tip:** Zoom in on your browser to see the output data more clearly as we work through each type.

## The Five n8n Data Types

n8n supports **five main data types**, each with its own symbol and use case:

1. **String** (📝) - Text and words
2. **Number** (#️⃣) - Numeric values  
3. **Boolean** (☑️) - True/false values
4. **Array** (📋) - Lists of items
5. **Object** (📦) - Complex structures containing multiple data types

## 1. String Data Type

### What is a String?

A **string is simply text** - any word, sentence, or character sequence. It's the most basic data type.

**Visual identifier:** Letter "A" symbol (📝)

### Creating a String Field

1. **In your Set node, click "Add Field"**
2. **Enter field name:** `name`
3. **Select data type:** `String` (should be default)
4. **Enter value:** `Nate`
5. **Click "Test Step"**

### Viewing String Output

**In Schema View:**
- You'll see: `name = Nate`
- **Symbol:** Letter "A" indicating string type

**In JSON View:**
- You'll see: `"name": "Nate"`
- **Key indicator:** Double quotes around the value `"Nate"`

**Remember:** Strings are always wrapped in double quotes in JSON format.

## 2. Number Data Type

### What is a Number?

A **number is any numeric value** - integers, decimals, positive, or negative values.

**Visual identifier:** Pound/hashtag symbol (#️⃣)

### Creating a Number Field

1. **Click "Add Field"** in your Set node
2. **Enter field name:** `age`
3. **Select data type:** `Number`
4. **Enter value:** `50`
5. **Click "Test Step"**

### Viewing Number Output

**In Schema View:**
- You'll see: `age = 50`
- **Symbol:** Pound sign (#) indicating number type

**In JSON View:**
- You'll see: `"age": 50`
- **Key indicator:** No quotes around the value, and it appears in green

### Why Number Type Matters

**Critical for filtering and logic:**
- ✅ **Correct:** `if age > 50` (works with number type)
- ❌ **Incorrect:** `if "50" > 50` (won't work if age is a string)

If your number comes through as a string, you can't perform mathematical operations or comparisons.

## 3. Boolean Data Type

### What is a Boolean?

A **boolean has only two possible values: true or false**. Perfect for yes/no, on/off, or status indicators.

**Visual identifier:** Checkbox symbol (☑️)

### Creating a Boolean Field

1. **Click "Add Field"** in your Set node
2. **Enter field name:** `adult`
3. **Select data type:** `Boolean`
4. **Notice:** You can only toggle between `true` and `false` - no typing allowed
5. **Select your choice** (true or false)
6. **Click "Test Step"**

### Viewing Boolean Output

**In Schema View:**
- You'll see: `adult = true` (or false)
- **Symbol:** Checkbox indicating boolean type

**In JSON View:**
- You'll see: `"adult": true`
- **Key indicator:** No quotes around true/false, appears in green

## 4. Array Data Type

### What is an Array?

An **array is a list of items** - like a shopping list or collection of names. Each item has a position number (starting from 0).

**Visual identifier:** List symbol (📋)

### Understanding Array Errors

**Common mistake:** If you try to put a single string in an array field, you'll get an error:

1. **Add a field named:** `names`
2. **Select data type:** `Array`
3. **Try entering:** `Nate`
4. **Click "Test Step"**
5. **See the error:** "Field 'names' expects an array but got a string"

### Creating a Proper Array

**Arrays must be formatted with square brackets and quotes:**

1. **In the names field, enter:** `["Nate"]`
   - **Square brackets** `[]` define the array
   - **Quotes** `""` define each string item
2. **Click "Test Step"**
3. **Success!** You now have an array with one item

### Adding Multiple Items to Arrays

**To add more names:**

1. **Modify your array:** `["Nate", "Sarah", "Mike"]`
   - **Comma separation** between items
   - **Each item in quotes**
2. **Click "Test Step"**

### Viewing Array Output

**In Schema View:**
- You'll see the array with expandable items
- Each item numbered: 0, 1, 2 (computers count from zero)

**In JSON View:**
- You'll see: `"names": ["Nate", "Sarah", "Mike"]`
- **Key indicator:** Square brackets `[]` containing comma-separated items

### Array vs String Conversion

**If you get array errors, you can:**
1. **Check "Ignore type conversions"** at the bottom of the Set node
2. **This converts arrays to strings** - but you lose array functionality
3. **Better solution:** Format your data correctly as an array

## 5. Object Data Type

### What is an Object?

An **object is a complex structure** that can contain any combination of strings, numbers, booleans, arrays, and even other objects. Think of it as a container holding related information.

**Visual identifier:** Box/package symbol (📦)

### Creating an Object with AI Help

**Since objects are complex, let's use AI to generate one:**

1. **Go to ChatGPT**
2. **Ask:** "Give me an example JSON object to put into n8n"
3. **Copy the response**

### Adding the Object to n8n

1. **In your Set node, instead of "Add Field":**
2. **Click "Customize with JSON"** at the bottom
3. **Paste the JSON from ChatGPT**
4. **Click "Test Step"**

### Example Object Structure

Your object might look like this:

```json
{
  "name": "Nate Herk",
  "email": "nate@example.com", 
  "company": "True Horizon",
  "interests": ["AI", "Automation", "n8n", "YouTube Content"],
  "project": {
    "title": "AI Course",
    "status": "Active", 
    "deadline": "2024-12-31"
  }
}
```

### Understanding Object Components

**This single object contains:**

- **Strings:** `name`, `email`, `company` (text with quotes)
- **Array:** `interests` (list in square brackets)
- **Nested Object:** `project` (object within object in curly braces)

### Viewing Object Output

**In Schema View:**
- **Expandable sections** for complex parts
- **Different symbols** for each data type within the object
- **Clear hierarchy** showing nested structures

**In Table View:**
- **Single row** representing the entire object
- **Easy to read** format
- **Shows array items** as numbered (0, 1, 2)
- **Shows object fields** with different names

**In JSON View:**
- **Curly braces** `{}` indicate objects
- **Square brackets** `[]` indicate arrays within objects
- **Proper nesting** shows structure relationships

### Array vs Object Key Differences

**Arrays:**
- **Ordered lists** with numbered positions (0, 1, 2)
- **Same data type** typically (all strings, all numbers)
- **Access by position:** `interests[0]` = "AI"

**Objects:**
- **Named properties** with specific keys
- **Mixed data types** in one structure
- **Access by name:** `project.title` = "AI Course"

## Data Type Troubleshooting

### Common Error Messages

**"Field expects an object but got an array"**
- **Solution:** Change your data type or reformat your data

**"Field expects a number but got a string"**  
- **Solution:** Remove quotes from numbers or change data type

**"Field expects an array but got a string"**
- **Solution:** Wrap single items in brackets: `["item"]`

### Using "Ignore Type Conversions"

**When to use:**
- **Quick fixes** during testing
- **When you're not sure** about the correct format

**What it does:**
- **Converts everything to strings**
- **Prevents errors** but may break functionality
- **Use sparingly** - better to fix the root cause

### Best Practices

1. **Plan your data structure** before building
2. **Use consistent data types** throughout workflows
3. **Test individual nodes** before connecting workflows
4. **Ask AI tools for help** with complex JSON structures
5. **Use Schema view** for easiest reading during development

## Practical Applications

### When to Use Each Type

**String:**
- Names, addresses, descriptions
- Any text-based information
- IDs that won't be calculated

**Number:**
- Ages, prices, quantities
- Any value used in calculations
- Comparison operations

**Boolean:**
- Status indicators (active/inactive)
- Conditional logic (yes/no decisions)
- Feature flags (enabled/disabled)

**Array:**
- Lists of emails, names, products
- Multiple selections
- Tags or categories

**Object:**
- Complete records (customer info, orders)
- API responses
- Complex data structures

### Data Type Impact on Workflow Logic

**Wrong data types can break:**
- **Mathematical operations**
- **Conditional logic** (if/then statements)
- **Filtering and sorting**
- **API integrations**
- **Database operations**

## Key Takeaways

### Essential Concepts:

1. **Five data types:** String, Number, Boolean, Array, Object
2. **Visual indicators** help identify types in Schema view
3. **JSON formatting** shows type through quotes and brackets
4. **Type mismatches** cause workflow errors
5. **"Ignore type conversions"** is a temporary fix, not a solution

### Format Quick Reference:

- **String:** `"text in quotes"`
- **Number:** `42` (no quotes, green)
- **Boolean:** `true` or `false` (no quotes, green)
- **Array:** `["item1", "item2", "item3"]`
- **Object:** `{"key": "value", "nested": {...}}`

### Next Steps:

Now that you understand data types, you're ready to:
- **Build complex workflows** without type errors
- **Handle API responses** correctly
- **Create dynamic data structures**
- **Debug data flow issues** effectively

**Remember:** When in doubt about data formatting, use ChatGPT or other AI tools to help generate properly formatted JSON examples!
