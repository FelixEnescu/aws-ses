aws-ses
=======

NET::AWS::SES with region support

Original [NET::AWS::SES](https://metacpan.org/pod/Net::AWS::SES) uses a US East (Northern Virginia) region hardcoded in SES.pm. Added region support in constructor and respective accesor routine:

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

Region is optional, if not provided dafault is 'us-east-1'. Current list of Amazon Simple Email Service (Amazon SES) is here: http://docs.aws.amazon.com/general/latest/gr/rande.html#ses_region.
