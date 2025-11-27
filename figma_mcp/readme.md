# Figma MCP Server Connectivity.

Step 1: Generate Figma Personal Access Token (PAT)

a- Go to Figma.com and log in

b- Click your profile icon (top-right corner)

c- Select Settings

d- Click on the Security tab

e- Scroll down to Personal Access Tokens section

f- Make Sure to tick on all the checkboxes. If not you won't be able to access Figma

g- Click Generate new token

h- Give your token a name (e.g., "Gemini CLI Access")

i- Click Generate token

j- ⚠️ Copy the token immediately - you won't be able to see it again!

h- Save it somewhere safe.


# Step 2: Connect Figma MCP Server to Gemini CLI

Open your separate terminal and run the following command:

1- gemini (if already installed globaly)

2- Once gemini run in the terminal then run the below command.

-> gemini mcp add --transport http figma https://mcp.figma.com/mcp --header "Authorization: Bearer YOUR_TOKEN_HERE"

## Example

-> gemini mcp add --transport http figma https://mcp.figma.com/mcp --header "Authorization: Bearer figd_abc123xyz789"

-> Once command run successfully, then closed the terminal and open again. run the "gemini" command again. 

-> When gemini will run in terminal, so it will automatically open the browser for the Authentication msg.

![Authentication](<authentication successful.jpg>)

# Step 3: Verify Connection

Check if Figma MCP is connected successfully:

-> gemini mcp list

You should see:

🟢 figma - Ready (8 tools, 1 prompt)

![figma list](<mcp list.jpg>)

If you see this, you're all set! ✅


# 4 Steps to Copy Remote Figma design to your own Design Code

Copy Figma template from internet

Open the Template

Copy all the components from the left side.

Click on back to files from profile picture.

Click on design at the top

Paste the design you copied 

save the design with your desired name


# 5 Step 4: Prepare Your Figma File

Make Your File Accessible:

Open your Figma design file in the browser

Click the Share button (top-right)

Change settings to "Anyone with the link can view" (by Default)

Click Copy link

## Copy Frame Link:

Select the specific frame you want to convert to code

Right-click on the frame

Select "Copy link to selection"

Save this link - you'll need it in the next step

-> Example link format:

https://www.figma.com/design/abc123/MyProject?node-id=1-23&t=45567


# 6 Step 5: Generate Code from Figma Design

Run this command in your terminal:

gemini "Get the design context from [PASTE_YOUR_FIGMA_LINK] and generate HTML and CSS"

## Real Example:

gemini "Get the design context from https://www.figma.com/design/abRnucBMTsgblvDB6ymtd1/Hospital-Design?node-id=1-218 and generate HTML and CSS"


## What happens:

Gemini fetches your design structure from Figma

Extracts layout, colors, text, spacing, and styles

Generates clean, working HTML and CSS code

Displays the code in your terminal


# 7 Step 6: Customize Your Output (Optional)

For React Components:

gemini "Get design context from [YOUR_LINK] and generate React components with Tailwind CSS"

For Responsive Design:

gemini "Use get_design_context on [YOUR_LINK] and create mobile-responsive HTML and CSS"


# Quick Troubleshooting

Problem: "This figma file could not be accessed"

-> Solutions:

✅ Make sure your Figma file is shared as "Anyone with the link can view"

✅ Verify your PAT token has proper permissions

✅ Try with a file you own or have edit access to

✅ Use a public Figma Community file to test


## Problem: Figma shows as "Disconnected"

Solution:

Remove the connection:

gemini mcp remove figma

Re-add using Step 3 commands

Verify again with gemini mcp list


## Problem: Token doesn't work

Solution:

Generate a new token in Figma

Make sure you copy it correctly (no extra spaces)

Re-run Step 3 with the new token

## Summary Checklist
 
 Install Gemini CLI
 
 Create Figma PAT token
 
 Connect Figma to Gemini: gemini mcp add
 
 Verify connection: gemini mcp list
 
 Share Figma file publicly
 
 Copy frame link from Figma
 
 Run: gemini "Get design context from [LINK] and generate code"
 
 Save/use your generated code


## Available Figma Tools

When connected, you have access to these tools:

Tool	                        Purpose
get_design_context	        Main tool -     extracts design structure for code generation
get_screenshot	            Gets visual image of the design
get_metadata	            Gets file info, variables, and styles
get_variable_defs	        Extracts design tokens/variables
get_code_connect_map	    Links Figma components to actual code components
get_figjam	                Access FigJam diagrams content
whoami	                    Verify your Figma account connection


## Tips for Best Results

Be Specific: Tell Gemini exactly what framework/language you want

Use Clear Prompts: Mention responsive design, accessibility, or specific libraries

Start Small: Convert one frame at a time before doing entire pages

Iterate: If output isn't perfect, refine your prompt with more details

Save Your Work: Ask Gemini to save code to files for easy access


-> Example Prompts

## Basic HTML/CSS:

gemini "Get design context from [LINK] and generate semantic HTML5 and modern CSS"

## React with Tailwind:

gemini "Convert this Figma frame to React: [LINK]. Use Tailwind CSS and make it responsive"

## Next.js Component:

gemini "Create a Next.js component from [LINK] with TypeScript and Tailwind"

## Vue Component:

gemini "Generate a Vue 3 component with Composition API from [LINK]"

## Need Help?

Check Figma MCP Documentation

Visit Gemini CLI Documentation

Ask your instructor for assistance


# 🎉 Happy Coding! You're now ready to convert designs to code seamlessly!