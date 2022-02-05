# commandbox-letsencrypt

This project is to attemps to write an integration for creating a Cert using the Let's Encrypt service.

sample task runner to show how to load a jar file.

component {

  function run() {
    // https://github.com/xerial/sqlite-jdbc/releases
    classLoad( filesystemUtil.resolvepath( 'lib' ) );
		
    var myDSN = {
      class: 'org.sqlite.JDBC',
      connectionString: 'jdbc:sqlite:#filesystemUtil.resolvepath( '~/AppData/Local/GitHub/cache.db' )#'
    };
		
    query name='local.qry' datasource=myDSN { echo( "
        SELECT key, typename
        FROM main.CacheElement
        WHERE key = 'tracked-repositories'
    " ) }		
		
    print.line( formatterUtil.formatJSON( qry ) );
		
  }

}

## possible projects
https://github.com/shred/acme4j
https://www.futlabs.com/2021/09/21/How-to-use-ACME4J-to-get-SSL-certificate-automatically/
https://labs.detectify.com/2018/01/12/how-i-exploited-acme-tls-sni-01-issuing-lets-encrypt-ssl-certs-for-any-domain-using-shared-hosting/

