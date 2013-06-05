# NAME

MARC::Field::Normalize::NACO - Matching normalization for MARC::Field

# SYNOPSIS

    use MARC::Field;
    use MARC::Field::Normalize::NACO;

    my $field = MARC::Field->new(
        '100', ' ', ' ', a => 'Stephenson, Neal,', d => '1953-');
    my $normalized = $field->as_naco;
    my $custom = $field->as_naco(subfields => 'a');

# DESCRIPTION

MARC::Field::Normalize::NACO turns MARC::Field objects into
strings canonicalized into NACO format. This makes them
suitable for matching against an index of similarly normalized
fields.

The principal means of invoking is through the as\_naco() method
that the module injects into MARC::Field when loaded. A string
is returned.

This method takes an optional named parameter, subfields. The
value of this parameter should be something that fits nicely
into the regex qr/\[$subfields\]/, typically a range of letters.
The default value is "a-z68".

# AUTHOR

Clay Fouts <cfouts@khephera.net>

# COPYRIGHT

Copyright 2013 PTFS, Inc.

# LICENSE

This library is free software; you can redistribute it and/or modify
it under the same terms as Perl itself.

# SEE ALSO

- http://www.loc.gov/aba/pcc/naco/normrule-2.html
- MARC::Record
