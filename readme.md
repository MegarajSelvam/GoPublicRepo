# steps to use private modules:

    -> Create SSH Token in your machine and add this generated public key in github SSH Key
    -> SSH Config modification in gitconfig file
    	[url "ssh://git@github.com:USERNAME/GoPrivateRepo.git"]
    		insteadOf = https://github.com/USERNAME/GoPrivateRepo.git
    -> Set go environment variable for private go repository
    		go env -w GOPRIVATE=github.com/USERNAME/GoPrivateRepo
    -> SSL Certificate issue ->
    	Temportary Fix:  git config –global http.sslVerify false
    	Permanent Fix:   git config –system http.sslCAPath /absolute/path/to/git/certificates (not working)
    	https://www.clickssl.net/blog/ssl-certificate-problem-unable-to-get-local-issuer-certificate
    -> go get github.com/USERNAME/GoPrivateRepo/guidGenerator
