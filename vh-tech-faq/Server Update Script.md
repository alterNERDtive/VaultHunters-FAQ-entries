# Server Update Script

(If someone wants to do one for Windows, be my guest and I’ll add it here.)

1. Put script somewhere (e.g. in your server’s root folder).
2. Stop the server.
3. Run the script _from your server’s root folder_.
3. **Use at your own risk.**

```bash
#!/usr/bin/env bash
2	abort () {
3	  echo "${1:-An unexpected error occured.} Exiting …" >&2
4	  exit ${2:-1}
5	}
6	
7	usage () {
8	  echo """Usage: ${filename:$0} <file>
9	
10	Make sure to stop the server first.
11	
12	  file:   The updated server files from Curseforge.
13	"""
14	  exit ${1:-0}
15	}
16	
17	extract () {
18	  dir=${1}
19	  rm -rf ${dir}
20	  unzip "${_file}" ${dir}/\*
21	}
22	
23	terralith () {
24	  echo "Sky Vaults server detected, removing Terralith …"
25	  rm -f mods/Terralith*.jar
26	}
27	
28	[[ $# -eq 1 ]] || usage 1
29	_file=${1}
30	
31	[[ -f "server.properties" ]] || abort "Current directory does not seem to be a Minecraft server."
32	
33	unzip -l "${_file}" > /dev/null 2>&1
34	[[ $? -eq 0 ]] || abort "\"${_file}\" is not a valid zip file."
35	
36	echo "running update …"
37	stuff="config defaultconfigs mods patchouli_books scripts"
38	for dir in ${stuff}
39	do
40	  extract ${dir}
41	done
42	
43	grep 'the_vault\\:sky_vaults
44	skyblockbuilder\\:skyblock' server.properties > /dev/null 2>&1
45	[[ $? -eq 0 ]] && terralith
46	
47	exit 0
```
