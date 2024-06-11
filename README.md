## To convert .yaml file into helm chart use

- cat deployment.yaml | helmify mongodb

## Now your helm chart is ready. Deploy your mongodb helm chart with helm install command.

- helm install mongodb

## other commands

Example 1: 'kustomize build <kustomize_dir> | helmify mychart' 
  - will create 'mychart' directory with Helm chart from kustomize output.

Example 2: 'cat my-app.yaml | helmify mychart' 
  - will create 'mychart' directory with Helm chart from yaml file.

Example 3: 'helmify -f ./test_data/dir  mychart' 
  - will scan directory ./test_data/dir for files with k8s manifests and create 'mychart' directory with Helm chart.

Example 4: 'helmify -f ./test_data/dir -r  mychart' 
  - will scan directory ./test_data/dir recursively and  create 'mychart' directory with Helm chart.

Example 5: 'helmify -f ./test_data/dir -f ./test_data/sample-app.yaml -f ./test_data/dir/another_dir  mychart' 
  - will scan provided multiple files and directories and  create 'mychart' directory with Helm chart.

Example 6: 'awk 'FNR==1 && NR!=1  {print "---"}{print}' /my_directory/*.yaml | helmify mychart' 
  - will create 'mychart' directory with Helm chart from all yaml files in my_directory directory.
