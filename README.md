NET::AWS::SES
=============

NET::AWS::SES with region and Email::MIME support

## Email::MIME

NET::AWS::SES can use an Email::MIME object to send email:

```perl
my $msg = Email::MIME->new($msg_str_ref);
my $r = $ses->send( $msg );  
```


## Region

Original (version 0.03) [NET::AWS::SES](http://search.cpan.org/~sherzodr/Net-AWS-SES/lib/Net/AWS/SES.pm) uses a US East (Northern Virginia) region hardcoded in SES.pm. Added region support in constructor and respective accesor routine:

```perl
use Net::AWS::SES;

my $ses = Net::AWS::SES->new(
    access_key  => '...', 
    secret_key  => '...',
    region      => 'eu-west-1',
);

$reg =  $ses->region;

print "My region is $reg\n";
```

Region is optional, if not provided default is 'us-east-1'. Current list of Amazon Simple Email Service (Amazon SES) is here: http://docs.aws.amazon.com/general/latest/gr/rande.html#ses_region.
