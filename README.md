# Illumicut

PROGRAM SOURCE CODE INCLUDED IN ADAPTI

Illumicut is a C++ program specially designed to efficiently detect and remove forward and reverse sequencing primers in paired-end reconstructed sequences
for now, this program can only detect a single forward primer and a single reverse primer.

This version CANNOT detect primers containing indels (this will be implemented in the next version)

When the primer is detected, Illumicut remove it and everything before (or after if the reverse primer is detected)

It's possible to use degenerated nucleotides in the primer sequence (the program will be able to tell if a nucleotide correspond to a degenerated base like "X" for all)

Here the list of degenerated nuclotides the program will understand:
K (G or T)
M (A or C)
R (A or G)
Y (C or T)
S (C or G)
W (A or T)
B (C or G or T)
V (A or C or G)
H (A or C or T)
D (A or G or T)
X/I ( A or C or T or G)

WARNING : NEVER use N for all nucleotides, this will always be count as a mismatch !

The next section is the program command line help (can be obtained with this command : ./illumicut --help)

USAGE: 

   ./Illumicut  -f <fasta/fastq> -g <path> -s <path> -p <string> [-r
                <string>] [-u <path>] [-t <int>] [-c] [-i] [-a <int>] [-m
                <int>] [-l <int>] [-o <int>] [-d] [--] [--version] [-h]


Where: 

   -f <fasta/fastq>,  --fastx_in <fasta/fastq>
     (required)  Fasta or Fastq file input (REQUIRED)

   -g <path>,  --fastx_out <path>
     (required)  Fasta or Fastq output name (REQUIRED)

   -s <path>,  --scrap_out <path>
     (required)  Scrap Fasta or Fastq output name (REQUIRED)

   -p <string>,  --forward_primer <string>
     (required)  Forward Primer 5'->3' (REQUIRED)

   -r <string>,  --reverse_primer <string>
     Reverse Primer 5'->3' (REQUIRED if -i option not used)

   -u <path>,  --Report_txt <path>
     Report file output name (Optional)

   -t <int>,  --num_threads <int>
     Number of threads to use (Default: 1)

   -c,  --force_fasta
     Force output in fasta format (will be ignored if format already fasta)

   -i,  --ignore_reverse
     Program will not try to find reverse primer

   -a <int>,  --ambig_max <int>
     Maximal ambiguity count in trimmed sequence, -1 value bypass this
     filter (Default: 0)

   -m <int>,  --mismatch_max <int>
     Maximal mismatch in primer for recognition (Default: 0)

   -l <int>,  --min_length <int>
     Sequence minimum length after trim (Default: 0)

   -o <int>,  --max_offset <int>
     Maximal primers offset in sequence (max bp offset to check before
     stop) (Default: 5)

   -d,  --debug
     Display debug messages

   --,  --ignore_rest
     Ignores the rest of the labeled arguments following this flag.

   --version
     Displays version information and exits.

   -h,  --help
     Displays usage information and exits.


   This program trim the forward and the reverse sequencing primers and
   everything before and after


If you have any questions concerning this program, you send a mail to Patrick Gagné (patg97@hotmail.com)

In case of problem with the program, please open an issue in the Illumicut Github


Licence information :

FREEWARE LICENSE
END-USER LICENSE AGREEMENT
For Illumicut
By Patrick Gagné

NOTICE TO USER:
Please, read this carefully. By using all or any portion of the Software you accept all the terms and conditions of this Agreement. If you do not agree, do not use this Software.

1. DEFINITIONS
When used in this Agreement, the following terms shall have the respective meanings indicated, such meanings to be applicable to both the singular and plural forms of the terms defined:

“Licensor” means Patrick Gagné.

“Licensee” means You or Your Company, unless otherwise indicated.

“Software” means (a) Illumicut

“Use” or “Using” means to access, install, download, copy or otherwise benefit from using the functionality of the Software in accordance with the Documentation.

“System” means Windows OS, GNU/Linux or Mac OS X, or any virtual machine.

2. GENERAL USE 
You are granted a non-exclusive License to Use the downloaded Software for any purposes for an unlimited period of time.

The software product under this License is provided free of charge. Even though a license fee is not paid for the use of such software, it does not mean that there are no conditions for using such software.

2.1. The Software may be installed and Used by the Licensee for any legal purpose.

2.2. The Software may be installed and Used by the Licensee on any number of systems.

2.3. The Software can be copied and distributed under the condition that original copyright notice and disclaimer of warranty will stay intact and the Licensee will not charge money or fees for the Software product, except to cover distribution costs.

2.4. The Licensee will not have any proprietary rights in and to the Software. The Licensee acknowledges and agrees that the Licensor retains all copyrights and other proprietary rights in and to the Software.

2.5 Use within the scope of this License is free of charge and no royalty or licensing fees shall be paid by the Licensee.

3. INTELLECTUAL PROPERTY RIGHTS
3.1 This License does not transmit any intellectual rights on the Software. The Software and any copies that the Licensee is authorized by the Licensor to make are the intellectual property of and are owned by the Licensor.

3.2 The Software is protected by copyright, including without limitation by Copyright Law and international treaty provisions.

3.3 Any copies that the Licensee is permitted to make pursuant to this Agreement must contain the same copyright and other proprietary notices that appear on or in the Software.

3.4 The structure, organization and code of the Software are the valuable trade secrets and confidential information of the Licensor. The Licensee agrees not to decompile, disassemble or otherwise attempt to discover the source code of the Software.

3.5 Any attempts to reverse-engineer, copy, clone, modify or alter in any way the installer program without the Licensor’s specific approval are strictly prohibited. The Licensee is not authorized to use any plug-in or enhancement that permits to save modifications to a file with software licensed and distributed by the Licensor.

3.6 Trademarks shall be used in accordance with accepted trademark practice, including identification of trademarks owners’ names. Trademarks can only be used to identify printed output produced by the Software and such use of any trademark does not give the Licensee any rights of ownership in that trademark.

4. WARRANTY
4.1 The Licensor warrants that:

4.1.1 The Licensor owns the Software and documentation and/or is in possession of valid and existing licenses that support the terms of this Agreement;

4.1.2 the Software conforms to specifications and functionality as specified in Documentation;

4.1.3 to the best of the Licensor’s knowledge, the Software does not infringe upon or violate any intellectual property right of any third party;

4.1.4 the Software does not contain any routine, intentionally designed by the Licensor to disable a computer program, or computer instructions that may alter, destroy or inhibit the processing environment.

4.2 Except those warranties specified in section 4.1 above, the Software is being delivered to the Licensee “AS IS” and the Licensor makes no warranty as to its use or performance.

The Licensor does not and cannot warrant the performance or results the Licensee may obtain by using the Software. The entire risk arising out of use or performance of the Software remains with the Licensee.

The Licensor gives no warranty, express or implied, that (i) the Software will be of satisfactory quality, suitable for any particular purpose or for any particular use under specified conditions, notwithstanding that such purpose, use, or conditions may be known to the Licensor; or (ii) that the Software will operate error free or without interruption or that any errors will be corrected.

5. LIMITATION OF LIABILITY
In no event will the Licensor be liable for any damages, claims or costs whatsoever or any consequential, indirect, incidental damages, or any lost profits or lost savings, even if the Licensor has been advised of the possibility of such loss, damages, claims or costs or for any claim by any third party.

In no event will the Licensee be liable to the Licensor on condition that the Licensee complies with all terms and conditions stated in this License.

6. NON-WAIVER
If a portion of this agreement is held unenforceable, the remainder shall be valid. It means that if one section of the Agreement is not lawful, the rest of the Agreement is still in force. A party’s failure to exercise any right under this Agreement will not constitute a waiver of (a) any other terms or conditions of this Agreement, or (b) a right at any time thereafter to require exact and strict compliance with the terms of this Agreement.
