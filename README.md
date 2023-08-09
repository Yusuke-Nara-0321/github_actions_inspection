# github_actions_inspection

メモ置き場

# echo "::set-output name=release_note::$(curl -X POST -H 'Accept: application/vnd.github.v3+json' -H 'Authorization: token ${{ secrets.GITHUB_TOKEN }}' https://api.github.com/repos/${{ github.repository }}/releases/generate-notes -d '{"tag_name":"${{ steps.release_tag.outputs.release_tag }}", "previous_tag_name":"${{ steps.pre_tag.outputs.pre_tag }}"}' | jq .body | sed 's/"//g')"
