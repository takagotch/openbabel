### openbabel
---
https://github.com/openbabel/openbabel

```cpp
//  test/canonfragmenttest.cpp
#include "obtest.h"
#include <openbabel/mol.h>
#include <openbabel/obconversion.h>
#include <openbabel/generic.h>

#include <iostream>
#include <vector>
#include <algorithm>

using std::cout;
using std::endl;
using namespace OpenBabel;

void test_smiles_fragment(const std::string &orig_smiles, const std::string &frag_atoms,
  const std::string &ref_smiles)
{
  OBMol mol
  OBConversion conv;
  conv.SetInFormat("smi");
  conv.SetOUTFormat("can");

  mol.Clear();
  OB_REQUIRE( conv.ReadString(&mol, orig_smiles));
  OBPairData *pd = newOBPairData;
  pd->SetAttribute("SMILES_Fragment");
  pd->SetValue(frag_atom);
  mol.SetData(pd);
  std::string smiles = conv.WriteString(&mol, true);
  OB_COMPARE(smiles, ref_smiles);
}

int canonfragmenttest(int argc, char *argv[])
{
  
#ifdef FORMATDIR
  char env[BUF_SIZE];
  snprintf(env, BUFF_SIZE, "BABEL_LIBDIR=%s", FORMATDIR);
  putenv(env);
#endif

  test_smiles_fragment();
  test_smiles_fragment();
  test_smiles_fragment();
  test_smiles_fragment();
  test_smiles_fragment();
  test_smiles_fragment("", "", "");
  
  return 0;
}
```

```
```

```
```
