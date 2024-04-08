根据震源和场地输入模拟空间相关的烈度分布，输入参数依次为震源信息和场地信息的文件名，例如 EQSource.txt，SiteFile.txt

EQSource.txt 每行依次为(空格分开)：
    ifmedian - 0/1是否输出中位值\
    M - 震级\
    N_sim - 次数\
    seed - int, 随机数种子\
    lon_0，lat_0 - 震中经纬度，°\
    W - down-dip width of the fault rupture plane. if unknown, input: 999\
    length - 断裂面水平方向长度\
    RuptureNormal_x, RuptureNormal_y, RuptureNormal_z - 断裂面朝上的法线方向（向东为x,向北为y,向上为z）\
    lambda - rake angle (degree) - average angle of slip measured in the plane of rupture\
    Fhw - hanging wall effect
        = 1 for including
        = 0 for excluding\
    Zhyp - (km) Hypocentral depth of the earthquake measured from sea level if unknown, input: 999\
    region
        = 0 for global (incl. Taiwan)
        = 1 for California
        = 3 for China or Turkey
        = 4 for Italy\
    nPCs - IM相关性PCA方法模拟考虑的主成分阶数，推荐大于等于5

SiteFile.txt 每行为一个场地的数据，每一行空格分开依次为:
    ID - int\
    lon - 经度\
    lat - 纬度\
    elevation_km - 高程\
    period1 - 基本周期\
    Vs30_mpers - 剪切波速\
    Z25_km - Depth to the 2.5 km/s shear-wave velocity horizon (km) 
    if in California or Japan and Z2.5 is unknow, then input: 999）