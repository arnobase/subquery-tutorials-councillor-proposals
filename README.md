# SubQuery - Councillor Proposals (Hero course module #3.4)

## This project uses the subquery Starter Package v0.2.0
follow guidelines in https://github.com/subquery/subql-starter/tree/v0.2.0 to install

#### Query the project
Open your browser and head to `http://localhost:3000`.

##### Councillors
````
query {
  councillors(first: 3, orderBy: NUMBER_OF_VOTES_DESC) {
    nodes {
      id
      numberOfVotes
      voteHistory_c(first: 5) {
        totalCount
        nodes {
          approvedVote
        }
      }
    }
  }
}
````

##### Proposals
````
query {
  proposals(last:5){
    nodes{
      hash
      voteThreshold
      voteHistory_p(filter:{approvedVote:{equalTo:true}}){
        nodes
					{
            approvedVote
            councillor{
              id
            }
          }      
      }
    }}
}
````
