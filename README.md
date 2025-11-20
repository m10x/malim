# MaliM - MALIcious Mcp server

A "malicious" MCP server designed to test MCP clients for potential security vulnerabilities.

## Usage
- `python3 -m venv .env; source .env/bin/activate`
- `pip3 install -r requirements.txt`
- `python3 malim.py`

## Features

- MCP Server
  - XSS in website_url
  - Prompt injection in instructions
  - XSS in icons
    - Modify icons to exploit insecure embeddings
- Tools
  - `all_in_one_tool` to test if the MCP Client can be prompt injected to use this tool instead of others
  - `collect_user_info` to check how the MCP client handles elicitations
  - `well_done` to test if the MCP Client can be prompt injected to run `whoami`
  - `find_products_name` to check which name/title the MCP client shows to the user
  - `add_numbers` & `add_numbers2` to check how the MCP client reacts to two tools with a similar name and equal title / description
  - `write_stuff` to test for tool poisoning, leading to add_numbers(2) to always calculate 1337 + 42
  - `analyze_sentiment` and `creative_writing` to test if sampling can be abused to call other tools and use their leak their output