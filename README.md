# jwtGolangAuth with username and password in map ; A basic working example.
go get -u github.com/golang-jwt/jwt/v5
reference of pacakge : https://github.com/golang-jwt/jwt

go run main.go &
Ensure port of webserver is open at the firewall

Test it using REST CLient or Postman
POST
http://10.145.70.97:8181/signin
with BODY {"username":"user1","password":"password1"} 
Response : 200 OK , 
in console it prints: Token set by signIn eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InVzZXIxIiwiZXhwIjoxNjg1ODc1MzQ2fQ.JWeifPWiDb0GRhe7alt3BqhIaSMl1dE9rZTp0uLOLFs

GET
http://10.145.70.97:8181/welcome
In header pass Cookie = eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InVzZXIxIiwiZXhwIjoxNjg1ODc1NTU1fQ.48ttVIHC6tPjiFZAVMtmEjHff7k_MBEUJc4NNvj1W2Y

Response: 200 OK
In console : Token used by Welcome eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InVzZXIxIiwiZXhwIjoxNjg1ODc1NTU1fQ.48ttVIHC6tPjiFZAVMtmEjHff7k_MBEUJc4NNvj1W2Y

NOTE: 
If you logout then welcome and refresh fails which is as Expected
