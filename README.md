void ProviderDB::processTransactions(const char* fileName[])
{
    string transType;
    string Speciality;
    string Num;
    int countOfProviders=0;
    
    ifstream tranFile;
    tranFile.open("transactions.txt");
    
    while( tranFile >> transType)
    {
        if (transType == "all")
        {
            ProviderDB sortByName;
            sortByName.print();
        }
        else if (transType == "specialty")
        {
            tranFile >> ws;
            getline(tranFile, Speciality);
            sortBySpecialty();
        
             int i, j;
            Provider bucket;
            
            for (i=1; i < countOfProviders; i++)
            {
                bucket = providerArray[i];
                
                for (j = i; j > 0; j--)
                {
                    if (strcmp(providerArray[j-1].getSpecialty(), Speciality) == 0)
                    {
                        countOfProviders++;
                    }
                }
                Speciality.print();
            }
            countOfProviders.print();
        }
        else if (transType == "number")
        {
            tranFile >> ws;
            tranFile >> Num;
            
            int searchNum;
            
            sortByProviderNumber();
            
            int searchForProviderNumber(char providerArray[searchNum]);
        }
    }
}

