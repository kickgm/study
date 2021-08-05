# study
# csv파일 합치기 방법
import os
import csv
import pandas as pd
import glob


input_file =  r'C:\studio code\Sunga_S'
output_file = r'C:\studio code\result3.csv'

allfile_list = glob.glob(os.path.join(input_file, '*.csv'))
print(allfile_list)
alldata = []
for file in allfile_list:
    df = pd.read_csv(file)
    alldata.append(df)

dataCombine = pd.concat(alldata,axis=0,ignore_index=True)
dataCombine.to_csv(output_file,index=False)
