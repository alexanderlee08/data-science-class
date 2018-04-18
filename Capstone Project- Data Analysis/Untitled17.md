

```python
import pandas as pd
import matplotlib.pyplot as plt
import numpy as np

iter_csv = pd.read_csv('Google Drive/CryptocoinsHistoricalPrices.csv',chunksize=1000)
df = pd.concat([chunk for chunk in iter_csv])
```


```python
import matplotlib.pyplot as plt
import numpy as np
```


```python
listed = dict()
dates = list()
index = 0
for index in range(len(df)):
    if (index % 5) == 0:
        row = df.iloc[index]
        if row['coin'] not in listed.keys():
            listed[row['coin']] = dict()
        listed[row['coin']][row['Date']] = row['High']
        #listed[row['coin']].append(row['High'])
        if row['Date'] not in dates:
            dates.append(row['Date'])
```


```python
newlist = sorted(dates) 
unique = dict()
for key in listed.keys():
    index = 0
    unique[key] = list()
    value = 0.0
    for day in newlist:
        if day not in listed[key].keys():
            unique[key].append(value)
        else:
            #print(listed[key][this]['high'])
            #print(unique[key].dtype)
            #print(listed[key][this]['high'])
            unique[key].append(listed[key][day])
            value = listed[key][day]
        index += 1

```


```python
last = 1
btc = list()
non = 1
for item in unique['BTC']:
    if item == last:
        btc.append(non)
    else:
        non = item / last
        btc.append(non)
    last = item
#print(btc)
#print(np.var(btc))

last = 1
non = 1
for key in unique.keys():
    eth = list()
    if key != 'BTC':
        index = 0
        for item in unique[key]:
            if index < 2000:
                if item == last:
                    eth.append(non)
                else:
                    if (last != 0):
                        non = item / last
                    eth.append(non)
                last = item
            index += 1
    plt.figure(figsize=(18, 5))
    #plt.plot(s, btc, marker='o', linestyle='--', color='r')
    plt.plot(btc, color='red')
    plt.plot(eth, color='blue')
    plt.title(key)
    plt.show()
    #print(eth.var())
#print(btc)
```

    c:\users\generic\appdata\local\programs\python\python36-32\lib\site-packages\ipykernel_launcher.py:8: RuntimeWarning: divide by zero encountered in double_scalars
      
    


![png](output_4_1.png)



![png](output_4_2.png)



![png](output_4_3.png)



![png](output_4_4.png)



![png](output_4_5.png)



![png](output_4_6.png)



![png](output_4_7.png)



![png](output_4_8.png)



![png](output_4_9.png)



![png](output_4_10.png)



![png](output_4_11.png)



![png](output_4_12.png)



![png](output_4_13.png)



![png](output_4_14.png)



![png](output_4_15.png)



![png](output_4_16.png)



![png](output_4_17.png)



![png](output_4_18.png)



![png](output_4_19.png)



![png](output_4_20.png)



![png](output_4_21.png)



![png](output_4_22.png)



![png](output_4_23.png)



![png](output_4_24.png)



![png](output_4_25.png)



![png](output_4_26.png)



![png](output_4_27.png)



![png](output_4_28.png)



![png](output_4_29.png)



![png](output_4_30.png)



![png](output_4_31.png)



![png](output_4_32.png)



![png](output_4_33.png)



![png](output_4_34.png)



![png](output_4_35.png)



![png](output_4_36.png)



![png](output_4_37.png)



![png](output_4_38.png)



![png](output_4_39.png)



![png](output_4_40.png)



![png](output_4_41.png)



![png](output_4_42.png)



![png](output_4_43.png)



![png](output_4_44.png)



![png](output_4_45.png)



![png](output_4_46.png)



![png](output_4_47.png)



![png](output_4_48.png)



![png](output_4_49.png)



![png](output_4_50.png)



![png](output_4_51.png)



![png](output_4_52.png)



![png](output_4_53.png)



![png](output_4_54.png)



![png](output_4_55.png)



![png](output_4_56.png)



![png](output_4_57.png)



![png](output_4_58.png)



![png](output_4_59.png)



![png](output_4_60.png)



![png](output_4_61.png)



![png](output_4_62.png)



![png](output_4_63.png)



![png](output_4_64.png)



![png](output_4_65.png)



![png](output_4_66.png)



![png](output_4_67.png)



![png](output_4_68.png)



![png](output_4_69.png)



![png](output_4_70.png)



![png](output_4_71.png)



![png](output_4_72.png)



![png](output_4_73.png)



![png](output_4_74.png)



![png](output_4_75.png)



![png](output_4_76.png)



![png](output_4_77.png)



![png](output_4_78.png)



![png](output_4_79.png)



![png](output_4_80.png)



![png](output_4_81.png)



![png](output_4_82.png)



![png](output_4_83.png)



![png](output_4_84.png)



![png](output_4_85.png)



![png](output_4_86.png)



![png](output_4_87.png)



![png](output_4_88.png)



![png](output_4_89.png)



![png](output_4_90.png)



![png](output_4_91.png)



![png](output_4_92.png)



![png](output_4_93.png)



![png](output_4_94.png)



![png](output_4_95.png)



![png](output_4_96.png)



![png](output_4_97.png)



![png](output_4_98.png)



![png](output_4_99.png)



![png](output_4_100.png)



![png](output_4_101.png)



![png](output_4_102.png)



![png](output_4_103.png)



![png](output_4_104.png)



![png](output_4_105.png)



![png](output_4_106.png)



![png](output_4_107.png)



![png](output_4_108.png)



![png](output_4_109.png)



![png](output_4_110.png)



![png](output_4_111.png)



![png](output_4_112.png)



![png](output_4_113.png)



![png](output_4_114.png)



![png](output_4_115.png)



![png](output_4_116.png)



![png](output_4_117.png)



![png](output_4_118.png)



![png](output_4_119.png)



![png](output_4_120.png)



![png](output_4_121.png)



![png](output_4_122.png)



![png](output_4_123.png)



![png](output_4_124.png)



![png](output_4_125.png)



![png](output_4_126.png)



![png](output_4_127.png)



![png](output_4_128.png)



![png](output_4_129.png)



![png](output_4_130.png)



![png](output_4_131.png)



![png](output_4_132.png)



![png](output_4_133.png)



![png](output_4_134.png)



![png](output_4_135.png)



![png](output_4_136.png)



![png](output_4_137.png)



![png](output_4_138.png)



![png](output_4_139.png)



![png](output_4_140.png)



![png](output_4_141.png)



![png](output_4_142.png)



![png](output_4_143.png)



![png](output_4_144.png)



![png](output_4_145.png)



![png](output_4_146.png)



![png](output_4_147.png)



![png](output_4_148.png)



![png](output_4_149.png)



![png](output_4_150.png)



![png](output_4_151.png)



![png](output_4_152.png)



![png](output_4_153.png)



![png](output_4_154.png)



![png](output_4_155.png)



![png](output_4_156.png)



![png](output_4_157.png)



![png](output_4_158.png)



![png](output_4_159.png)



![png](output_4_160.png)



![png](output_4_161.png)



![png](output_4_162.png)



![png](output_4_163.png)



![png](output_4_164.png)



![png](output_4_165.png)



![png](output_4_166.png)



![png](output_4_167.png)



![png](output_4_168.png)



![png](output_4_169.png)



![png](output_4_170.png)



![png](output_4_171.png)



![png](output_4_172.png)



![png](output_4_173.png)



![png](output_4_174.png)



![png](output_4_175.png)



![png](output_4_176.png)



![png](output_4_177.png)



![png](output_4_178.png)



![png](output_4_179.png)



![png](output_4_180.png)



![png](output_4_181.png)



![png](output_4_182.png)



![png](output_4_183.png)



![png](output_4_184.png)



![png](output_4_185.png)



![png](output_4_186.png)



![png](output_4_187.png)



![png](output_4_188.png)



![png](output_4_189.png)



![png](output_4_190.png)



![png](output_4_191.png)



![png](output_4_192.png)



![png](output_4_193.png)



![png](output_4_194.png)



![png](output_4_195.png)



![png](output_4_196.png)



![png](output_4_197.png)



![png](output_4_198.png)



![png](output_4_199.png)



![png](output_4_200.png)



![png](output_4_201.png)



![png](output_4_202.png)



![png](output_4_203.png)



![png](output_4_204.png)



![png](output_4_205.png)



![png](output_4_206.png)



![png](output_4_207.png)



![png](output_4_208.png)



![png](output_4_209.png)



![png](output_4_210.png)



![png](output_4_211.png)



![png](output_4_212.png)



![png](output_4_213.png)



![png](output_4_214.png)



![png](output_4_215.png)



![png](output_4_216.png)



![png](output_4_217.png)



![png](output_4_218.png)



![png](output_4_219.png)



![png](output_4_220.png)



![png](output_4_221.png)



![png](output_4_222.png)



![png](output_4_223.png)



![png](output_4_224.png)



![png](output_4_225.png)



![png](output_4_226.png)



![png](output_4_227.png)



![png](output_4_228.png)



![png](output_4_229.png)



![png](output_4_230.png)



![png](output_4_231.png)



![png](output_4_232.png)



![png](output_4_233.png)



![png](output_4_234.png)



![png](output_4_235.png)



![png](output_4_236.png)



![png](output_4_237.png)



![png](output_4_238.png)



![png](output_4_239.png)



![png](output_4_240.png)



![png](output_4_241.png)



![png](output_4_242.png)



![png](output_4_243.png)



![png](output_4_244.png)



![png](output_4_245.png)



![png](output_4_246.png)



![png](output_4_247.png)



![png](output_4_248.png)



![png](output_4_249.png)



![png](output_4_250.png)



![png](output_4_251.png)



![png](output_4_252.png)



![png](output_4_253.png)



![png](output_4_254.png)



![png](output_4_255.png)



![png](output_4_256.png)



![png](output_4_257.png)



![png](output_4_258.png)



![png](output_4_259.png)



![png](output_4_260.png)



![png](output_4_261.png)



![png](output_4_262.png)



![png](output_4_263.png)



![png](output_4_264.png)



![png](output_4_265.png)



![png](output_4_266.png)



![png](output_4_267.png)



![png](output_4_268.png)



![png](output_4_269.png)



![png](output_4_270.png)



![png](output_4_271.png)



![png](output_4_272.png)



![png](output_4_273.png)



![png](output_4_274.png)



![png](output_4_275.png)



![png](output_4_276.png)



![png](output_4_277.png)



![png](output_4_278.png)



![png](output_4_279.png)



![png](output_4_280.png)



![png](output_4_281.png)



![png](output_4_282.png)



![png](output_4_283.png)



![png](output_4_284.png)



![png](output_4_285.png)



![png](output_4_286.png)



![png](output_4_287.png)



![png](output_4_288.png)



![png](output_4_289.png)



![png](output_4_290.png)



![png](output_4_291.png)



![png](output_4_292.png)



![png](output_4_293.png)



![png](output_4_294.png)



![png](output_4_295.png)



![png](output_4_296.png)



![png](output_4_297.png)



![png](output_4_298.png)



![png](output_4_299.png)



![png](output_4_300.png)



![png](output_4_301.png)



![png](output_4_302.png)



![png](output_4_303.png)



![png](output_4_304.png)



![png](output_4_305.png)



![png](output_4_306.png)



![png](output_4_307.png)



![png](output_4_308.png)



![png](output_4_309.png)



![png](output_4_310.png)



![png](output_4_311.png)



![png](output_4_312.png)



![png](output_4_313.png)



![png](output_4_314.png)



![png](output_4_315.png)



![png](output_4_316.png)



![png](output_4_317.png)



![png](output_4_318.png)



![png](output_4_319.png)



![png](output_4_320.png)



![png](output_4_321.png)



![png](output_4_322.png)



![png](output_4_323.png)



![png](output_4_324.png)



![png](output_4_325.png)



![png](output_4_326.png)



![png](output_4_327.png)



![png](output_4_328.png)



![png](output_4_329.png)



![png](output_4_330.png)



![png](output_4_331.png)



![png](output_4_332.png)



![png](output_4_333.png)



![png](output_4_334.png)



![png](output_4_335.png)



![png](output_4_336.png)



![png](output_4_337.png)



![png](output_4_338.png)



![png](output_4_339.png)



![png](output_4_340.png)



![png](output_4_341.png)



![png](output_4_342.png)



![png](output_4_343.png)



![png](output_4_344.png)



![png](output_4_345.png)



![png](output_4_346.png)



![png](output_4_347.png)



![png](output_4_348.png)



![png](output_4_349.png)



![png](output_4_350.png)



![png](output_4_351.png)



![png](output_4_352.png)



![png](output_4_353.png)



![png](output_4_354.png)



![png](output_4_355.png)



![png](output_4_356.png)



![png](output_4_357.png)



![png](output_4_358.png)



![png](output_4_359.png)



![png](output_4_360.png)



![png](output_4_361.png)



![png](output_4_362.png)



![png](output_4_363.png)



![png](output_4_364.png)



![png](output_4_365.png)



![png](output_4_366.png)



![png](output_4_367.png)



![png](output_4_368.png)



![png](output_4_369.png)



![png](output_4_370.png)



![png](output_4_371.png)



![png](output_4_372.png)



![png](output_4_373.png)



![png](output_4_374.png)



![png](output_4_375.png)



![png](output_4_376.png)



![png](output_4_377.png)



![png](output_4_378.png)



![png](output_4_379.png)



![png](output_4_380.png)



![png](output_4_381.png)



![png](output_4_382.png)



![png](output_4_383.png)



![png](output_4_384.png)



![png](output_4_385.png)



![png](output_4_386.png)



![png](output_4_387.png)



![png](output_4_388.png)



![png](output_4_389.png)



![png](output_4_390.png)



![png](output_4_391.png)



![png](output_4_392.png)



![png](output_4_393.png)



![png](output_4_394.png)



![png](output_4_395.png)



![png](output_4_396.png)



![png](output_4_397.png)



![png](output_4_398.png)



![png](output_4_399.png)



![png](output_4_400.png)



![png](output_4_401.png)



![png](output_4_402.png)



![png](output_4_403.png)



![png](output_4_404.png)



![png](output_4_405.png)



![png](output_4_406.png)



![png](output_4_407.png)



![png](output_4_408.png)



![png](output_4_409.png)



![png](output_4_410.png)



![png](output_4_411.png)



![png](output_4_412.png)



![png](output_4_413.png)



![png](output_4_414.png)



![png](output_4_415.png)



![png](output_4_416.png)



![png](output_4_417.png)



![png](output_4_418.png)



![png](output_4_419.png)



![png](output_4_420.png)



![png](output_4_421.png)



![png](output_4_422.png)



![png](output_4_423.png)



![png](output_4_424.png)



![png](output_4_425.png)



![png](output_4_426.png)



![png](output_4_427.png)



![png](output_4_428.png)



![png](output_4_429.png)



![png](output_4_430.png)



![png](output_4_431.png)



![png](output_4_432.png)



![png](output_4_433.png)



![png](output_4_434.png)



![png](output_4_435.png)



![png](output_4_436.png)



![png](output_4_437.png)



![png](output_4_438.png)



![png](output_4_439.png)



![png](output_4_440.png)



![png](output_4_441.png)



![png](output_4_442.png)



![png](output_4_443.png)



![png](output_4_444.png)



![png](output_4_445.png)



![png](output_4_446.png)



![png](output_4_447.png)



![png](output_4_448.png)



![png](output_4_449.png)



![png](output_4_450.png)



![png](output_4_451.png)



![png](output_4_452.png)



![png](output_4_453.png)



![png](output_4_454.png)



![png](output_4_455.png)



![png](output_4_456.png)



![png](output_4_457.png)



![png](output_4_458.png)



![png](output_4_459.png)



![png](output_4_460.png)



![png](output_4_461.png)



![png](output_4_462.png)



![png](output_4_463.png)



![png](output_4_464.png)



![png](output_4_465.png)



![png](output_4_466.png)



![png](output_4_467.png)



![png](output_4_468.png)



![png](output_4_469.png)



![png](output_4_470.png)



![png](output_4_471.png)



![png](output_4_472.png)



![png](output_4_473.png)



![png](output_4_474.png)



![png](output_4_475.png)



![png](output_4_476.png)



![png](output_4_477.png)



![png](output_4_478.png)



![png](output_4_479.png)



![png](output_4_480.png)



![png](output_4_481.png)



![png](output_4_482.png)



![png](output_4_483.png)



![png](output_4_484.png)



![png](output_4_485.png)



![png](output_4_486.png)



![png](output_4_487.png)



![png](output_4_488.png)



![png](output_4_489.png)



![png](output_4_490.png)



![png](output_4_491.png)



![png](output_4_492.png)



![png](output_4_493.png)



![png](output_4_494.png)



![png](output_4_495.png)



![png](output_4_496.png)



![png](output_4_497.png)



![png](output_4_498.png)



![png](output_4_499.png)



![png](output_4_500.png)



![png](output_4_501.png)



![png](output_4_502.png)



![png](output_4_503.png)



![png](output_4_504.png)



![png](output_4_505.png)



![png](output_4_506.png)



![png](output_4_507.png)



![png](output_4_508.png)



![png](output_4_509.png)



![png](output_4_510.png)



![png](output_4_511.png)



![png](output_4_512.png)



![png](output_4_513.png)



![png](output_4_514.png)



![png](output_4_515.png)



![png](output_4_516.png)



![png](output_4_517.png)



![png](output_4_518.png)



![png](output_4_519.png)



![png](output_4_520.png)



![png](output_4_521.png)



![png](output_4_522.png)



![png](output_4_523.png)



![png](output_4_524.png)



![png](output_4_525.png)



![png](output_4_526.png)



![png](output_4_527.png)



![png](output_4_528.png)



![png](output_4_529.png)



![png](output_4_530.png)



![png](output_4_531.png)



![png](output_4_532.png)



![png](output_4_533.png)



![png](output_4_534.png)



![png](output_4_535.png)



![png](output_4_536.png)



![png](output_4_537.png)



![png](output_4_538.png)



![png](output_4_539.png)



![png](output_4_540.png)



![png](output_4_541.png)



![png](output_4_542.png)



![png](output_4_543.png)



![png](output_4_544.png)



![png](output_4_545.png)



![png](output_4_546.png)



![png](output_4_547.png)



![png](output_4_548.png)



![png](output_4_549.png)



![png](output_4_550.png)



![png](output_4_551.png)



![png](output_4_552.png)



![png](output_4_553.png)



![png](output_4_554.png)



![png](output_4_555.png)



![png](output_4_556.png)



![png](output_4_557.png)



![png](output_4_558.png)



![png](output_4_559.png)



![png](output_4_560.png)



![png](output_4_561.png)



![png](output_4_562.png)



![png](output_4_563.png)



![png](output_4_564.png)



![png](output_4_565.png)



![png](output_4_566.png)



![png](output_4_567.png)



![png](output_4_568.png)



![png](output_4_569.png)



![png](output_4_570.png)



![png](output_4_571.png)



![png](output_4_572.png)



![png](output_4_573.png)



![png](output_4_574.png)



![png](output_4_575.png)



![png](output_4_576.png)



![png](output_4_577.png)



![png](output_4_578.png)



![png](output_4_579.png)



![png](output_4_580.png)



![png](output_4_581.png)



![png](output_4_582.png)



![png](output_4_583.png)



![png](output_4_584.png)



![png](output_4_585.png)



![png](output_4_586.png)



![png](output_4_587.png)



![png](output_4_588.png)



![png](output_4_589.png)



![png](output_4_590.png)



![png](output_4_591.png)



![png](output_4_592.png)



![png](output_4_593.png)



![png](output_4_594.png)



![png](output_4_595.png)



![png](output_4_596.png)



![png](output_4_597.png)



![png](output_4_598.png)



![png](output_4_599.png)



![png](output_4_600.png)



![png](output_4_601.png)



![png](output_4_602.png)



![png](output_4_603.png)



![png](output_4_604.png)



![png](output_4_605.png)



![png](output_4_606.png)



![png](output_4_607.png)



![png](output_4_608.png)



![png](output_4_609.png)



![png](output_4_610.png)



![png](output_4_611.png)



![png](output_4_612.png)



![png](output_4_613.png)



![png](output_4_614.png)



![png](output_4_615.png)



![png](output_4_616.png)



![png](output_4_617.png)



![png](output_4_618.png)



![png](output_4_619.png)



![png](output_4_620.png)



![png](output_4_621.png)



![png](output_4_622.png)



![png](output_4_623.png)



![png](output_4_624.png)



![png](output_4_625.png)



![png](output_4_626.png)



![png](output_4_627.png)



![png](output_4_628.png)



![png](output_4_629.png)



![png](output_4_630.png)



![png](output_4_631.png)



![png](output_4_632.png)



![png](output_4_633.png)



![png](output_4_634.png)



![png](output_4_635.png)



![png](output_4_636.png)



![png](output_4_637.png)



![png](output_4_638.png)



![png](output_4_639.png)



![png](output_4_640.png)



![png](output_4_641.png)



![png](output_4_642.png)



![png](output_4_643.png)



![png](output_4_644.png)



![png](output_4_645.png)



![png](output_4_646.png)



![png](output_4_647.png)



![png](output_4_648.png)



![png](output_4_649.png)



![png](output_4_650.png)



![png](output_4_651.png)



![png](output_4_652.png)



![png](output_4_653.png)



![png](output_4_654.png)



![png](output_4_655.png)



![png](output_4_656.png)



![png](output_4_657.png)



![png](output_4_658.png)



![png](output_4_659.png)



![png](output_4_660.png)



![png](output_4_661.png)



![png](output_4_662.png)



![png](output_4_663.png)



![png](output_4_664.png)



![png](output_4_665.png)



![png](output_4_666.png)



![png](output_4_667.png)



![png](output_4_668.png)



![png](output_4_669.png)



![png](output_4_670.png)



![png](output_4_671.png)



![png](output_4_672.png)



![png](output_4_673.png)



![png](output_4_674.png)



![png](output_4_675.png)



![png](output_4_676.png)



![png](output_4_677.png)



![png](output_4_678.png)



![png](output_4_679.png)



![png](output_4_680.png)



![png](output_4_681.png)



![png](output_4_682.png)



![png](output_4_683.png)



![png](output_4_684.png)



![png](output_4_685.png)



![png](output_4_686.png)



![png](output_4_687.png)



![png](output_4_688.png)



![png](output_4_689.png)



![png](output_4_690.png)



![png](output_4_691.png)



![png](output_4_692.png)



![png](output_4_693.png)



![png](output_4_694.png)



![png](output_4_695.png)



![png](output_4_696.png)



![png](output_4_697.png)



![png](output_4_698.png)



![png](output_4_699.png)



![png](output_4_700.png)



![png](output_4_701.png)



![png](output_4_702.png)



![png](output_4_703.png)



![png](output_4_704.png)



![png](output_4_705.png)



![png](output_4_706.png)



![png](output_4_707.png)



![png](output_4_708.png)



![png](output_4_709.png)



![png](output_4_710.png)



![png](output_4_711.png)



![png](output_4_712.png)



![png](output_4_713.png)



![png](output_4_714.png)



![png](output_4_715.png)



![png](output_4_716.png)



![png](output_4_717.png)



![png](output_4_718.png)



![png](output_4_719.png)



![png](output_4_720.png)



![png](output_4_721.png)



![png](output_4_722.png)



![png](output_4_723.png)



![png](output_4_724.png)



![png](output_4_725.png)



![png](output_4_726.png)



![png](output_4_727.png)



![png](output_4_728.png)



![png](output_4_729.png)



![png](output_4_730.png)



![png](output_4_731.png)



![png](output_4_732.png)



![png](output_4_733.png)



![png](output_4_734.png)



![png](output_4_735.png)



![png](output_4_736.png)



![png](output_4_737.png)



![png](output_4_738.png)



![png](output_4_739.png)



![png](output_4_740.png)



![png](output_4_741.png)



![png](output_4_742.png)



![png](output_4_743.png)



![png](output_4_744.png)



![png](output_4_745.png)



![png](output_4_746.png)



![png](output_4_747.png)



![png](output_4_748.png)



![png](output_4_749.png)



![png](output_4_750.png)



![png](output_4_751.png)



![png](output_4_752.png)



![png](output_4_753.png)



![png](output_4_754.png)



![png](output_4_755.png)



![png](output_4_756.png)



![png](output_4_757.png)



![png](output_4_758.png)



![png](output_4_759.png)



![png](output_4_760.png)



![png](output_4_761.png)



![png](output_4_762.png)



![png](output_4_763.png)



![png](output_4_764.png)



![png](output_4_765.png)



![png](output_4_766.png)



![png](output_4_767.png)



![png](output_4_768.png)



![png](output_4_769.png)



![png](output_4_770.png)



![png](output_4_771.png)



![png](output_4_772.png)



![png](output_4_773.png)



![png](output_4_774.png)



![png](output_4_775.png)



![png](output_4_776.png)



![png](output_4_777.png)



![png](output_4_778.png)



![png](output_4_779.png)



![png](output_4_780.png)



![png](output_4_781.png)



![png](output_4_782.png)



![png](output_4_783.png)



![png](output_4_784.png)



![png](output_4_785.png)



![png](output_4_786.png)



![png](output_4_787.png)



![png](output_4_788.png)



![png](output_4_789.png)



![png](output_4_790.png)



![png](output_4_791.png)



![png](output_4_792.png)



![png](output_4_793.png)



![png](output_4_794.png)



![png](output_4_795.png)



![png](output_4_796.png)



![png](output_4_797.png)



![png](output_4_798.png)



![png](output_4_799.png)



![png](output_4_800.png)



![png](output_4_801.png)



![png](output_4_802.png)



![png](output_4_803.png)



![png](output_4_804.png)



![png](output_4_805.png)



![png](output_4_806.png)



![png](output_4_807.png)



![png](output_4_808.png)



![png](output_4_809.png)



![png](output_4_810.png)



![png](output_4_811.png)



![png](output_4_812.png)



![png](output_4_813.png)



![png](output_4_814.png)



![png](output_4_815.png)



![png](output_4_816.png)



![png](output_4_817.png)



![png](output_4_818.png)



![png](output_4_819.png)



![png](output_4_820.png)



![png](output_4_821.png)



![png](output_4_822.png)



![png](output_4_823.png)



![png](output_4_824.png)



![png](output_4_825.png)



![png](output_4_826.png)



![png](output_4_827.png)



![png](output_4_828.png)



![png](output_4_829.png)



![png](output_4_830.png)



![png](output_4_831.png)



![png](output_4_832.png)



![png](output_4_833.png)



![png](output_4_834.png)



![png](output_4_835.png)



![png](output_4_836.png)



![png](output_4_837.png)



![png](output_4_838.png)



![png](output_4_839.png)



![png](output_4_840.png)



![png](output_4_841.png)



![png](output_4_842.png)



![png](output_4_843.png)



![png](output_4_844.png)



![png](output_4_845.png)



![png](output_4_846.png)



![png](output_4_847.png)



![png](output_4_848.png)



![png](output_4_849.png)



![png](output_4_850.png)



![png](output_4_851.png)



![png](output_4_852.png)



![png](output_4_853.png)



![png](output_4_854.png)



![png](output_4_855.png)



![png](output_4_856.png)



![png](output_4_857.png)



![png](output_4_858.png)



![png](output_4_859.png)



![png](output_4_860.png)



![png](output_4_861.png)



![png](output_4_862.png)



![png](output_4_863.png)



![png](output_4_864.png)



![png](output_4_865.png)



![png](output_4_866.png)



![png](output_4_867.png)



![png](output_4_868.png)



![png](output_4_869.png)



![png](output_4_870.png)



![png](output_4_871.png)



![png](output_4_872.png)



![png](output_4_873.png)



![png](output_4_874.png)



![png](output_4_875.png)



![png](output_4_876.png)



![png](output_4_877.png)



![png](output_4_878.png)



![png](output_4_879.png)



![png](output_4_880.png)



![png](output_4_881.png)



![png](output_4_882.png)



![png](output_4_883.png)



![png](output_4_884.png)



![png](output_4_885.png)



![png](output_4_886.png)



![png](output_4_887.png)



![png](output_4_888.png)



![png](output_4_889.png)



![png](output_4_890.png)



![png](output_4_891.png)



![png](output_4_892.png)



![png](output_4_893.png)



![png](output_4_894.png)



![png](output_4_895.png)



![png](output_4_896.png)



![png](output_4_897.png)



![png](output_4_898.png)



![png](output_4_899.png)



![png](output_4_900.png)



![png](output_4_901.png)



![png](output_4_902.png)



![png](output_4_903.png)



![png](output_4_904.png)



![png](output_4_905.png)



![png](output_4_906.png)



![png](output_4_907.png)



![png](output_4_908.png)



![png](output_4_909.png)



![png](output_4_910.png)



![png](output_4_911.png)



![png](output_4_912.png)



![png](output_4_913.png)



![png](output_4_914.png)



![png](output_4_915.png)



![png](output_4_916.png)



![png](output_4_917.png)



![png](output_4_918.png)



![png](output_4_919.png)



![png](output_4_920.png)



![png](output_4_921.png)



![png](output_4_922.png)



![png](output_4_923.png)



![png](output_4_924.png)



![png](output_4_925.png)



![png](output_4_926.png)



![png](output_4_927.png)



![png](output_4_928.png)



![png](output_4_929.png)



![png](output_4_930.png)



![png](output_4_931.png)



![png](output_4_932.png)



![png](output_4_933.png)



![png](output_4_934.png)



![png](output_4_935.png)



![png](output_4_936.png)



![png](output_4_937.png)



![png](output_4_938.png)



![png](output_4_939.png)



![png](output_4_940.png)



![png](output_4_941.png)



![png](output_4_942.png)



![png](output_4_943.png)



![png](output_4_944.png)



![png](output_4_945.png)



![png](output_4_946.png)



![png](output_4_947.png)



![png](output_4_948.png)



![png](output_4_949.png)



![png](output_4_950.png)



![png](output_4_951.png)



![png](output_4_952.png)



![png](output_4_953.png)



![png](output_4_954.png)



![png](output_4_955.png)



![png](output_4_956.png)



![png](output_4_957.png)



![png](output_4_958.png)



![png](output_4_959.png)



![png](output_4_960.png)



![png](output_4_961.png)



![png](output_4_962.png)



![png](output_4_963.png)



![png](output_4_964.png)



![png](output_4_965.png)



![png](output_4_966.png)



![png](output_4_967.png)



![png](output_4_968.png)



![png](output_4_969.png)



![png](output_4_970.png)



![png](output_4_971.png)



![png](output_4_972.png)



![png](output_4_973.png)



![png](output_4_974.png)



![png](output_4_975.png)



![png](output_4_976.png)



![png](output_4_977.png)



![png](output_4_978.png)



![png](output_4_979.png)



![png](output_4_980.png)



![png](output_4_981.png)



![png](output_4_982.png)



![png](output_4_983.png)



![png](output_4_984.png)



![png](output_4_985.png)



![png](output_4_986.png)



![png](output_4_987.png)



![png](output_4_988.png)



![png](output_4_989.png)



![png](output_4_990.png)



![png](output_4_991.png)



![png](output_4_992.png)



![png](output_4_993.png)



![png](output_4_994.png)



![png](output_4_995.png)



![png](output_4_996.png)



![png](output_4_997.png)



![png](output_4_998.png)



![png](output_4_999.png)



![png](output_4_1000.png)



![png](output_4_1001.png)



![png](output_4_1002.png)



![png](output_4_1003.png)



![png](output_4_1004.png)



![png](output_4_1005.png)



![png](output_4_1006.png)



![png](output_4_1007.png)



![png](output_4_1008.png)



![png](output_4_1009.png)



![png](output_4_1010.png)



![png](output_4_1011.png)



![png](output_4_1012.png)



![png](output_4_1013.png)



![png](output_4_1014.png)



![png](output_4_1015.png)



![png](output_4_1016.png)



![png](output_4_1017.png)



![png](output_4_1018.png)



![png](output_4_1019.png)



![png](output_4_1020.png)



![png](output_4_1021.png)



![png](output_4_1022.png)



![png](output_4_1023.png)



![png](output_4_1024.png)



![png](output_4_1025.png)



![png](output_4_1026.png)



![png](output_4_1027.png)



![png](output_4_1028.png)



![png](output_4_1029.png)



![png](output_4_1030.png)



![png](output_4_1031.png)



![png](output_4_1032.png)



![png](output_4_1033.png)



![png](output_4_1034.png)



![png](output_4_1035.png)



![png](output_4_1036.png)



![png](output_4_1037.png)



![png](output_4_1038.png)



![png](output_4_1039.png)



![png](output_4_1040.png)



![png](output_4_1041.png)



![png](output_4_1042.png)



![png](output_4_1043.png)



![png](output_4_1044.png)



![png](output_4_1045.png)



![png](output_4_1046.png)



![png](output_4_1047.png)



![png](output_4_1048.png)



![png](output_4_1049.png)



![png](output_4_1050.png)



![png](output_4_1051.png)



![png](output_4_1052.png)



![png](output_4_1053.png)



![png](output_4_1054.png)



![png](output_4_1055.png)



![png](output_4_1056.png)



![png](output_4_1057.png)



![png](output_4_1058.png)



![png](output_4_1059.png)



![png](output_4_1060.png)



![png](output_4_1061.png)



![png](output_4_1062.png)



![png](output_4_1063.png)



![png](output_4_1064.png)



![png](output_4_1065.png)



![png](output_4_1066.png)



![png](output_4_1067.png)



![png](output_4_1068.png)



![png](output_4_1069.png)



![png](output_4_1070.png)



![png](output_4_1071.png)



![png](output_4_1072.png)



![png](output_4_1073.png)



![png](output_4_1074.png)



![png](output_4_1075.png)



![png](output_4_1076.png)



![png](output_4_1077.png)



![png](output_4_1078.png)



![png](output_4_1079.png)



![png](output_4_1080.png)



![png](output_4_1081.png)



![png](output_4_1082.png)



![png](output_4_1083.png)



![png](output_4_1084.png)



![png](output_4_1085.png)



![png](output_4_1086.png)



![png](output_4_1087.png)



![png](output_4_1088.png)



![png](output_4_1089.png)



![png](output_4_1090.png)



![png](output_4_1091.png)



![png](output_4_1092.png)



![png](output_4_1093.png)



![png](output_4_1094.png)



![png](output_4_1095.png)



![png](output_4_1096.png)



![png](output_4_1097.png)



![png](output_4_1098.png)



![png](output_4_1099.png)



![png](output_4_1100.png)



![png](output_4_1101.png)



![png](output_4_1102.png)



![png](output_4_1103.png)



![png](output_4_1104.png)



![png](output_4_1105.png)



![png](output_4_1106.png)



![png](output_4_1107.png)



![png](output_4_1108.png)



![png](output_4_1109.png)



![png](output_4_1110.png)



![png](output_4_1111.png)



![png](output_4_1112.png)



![png](output_4_1113.png)



![png](output_4_1114.png)



![png](output_4_1115.png)



![png](output_4_1116.png)



![png](output_4_1117.png)



![png](output_4_1118.png)



![png](output_4_1119.png)



![png](output_4_1120.png)



![png](output_4_1121.png)



![png](output_4_1122.png)



![png](output_4_1123.png)



![png](output_4_1124.png)



![png](output_4_1125.png)



![png](output_4_1126.png)



![png](output_4_1127.png)



![png](output_4_1128.png)



![png](output_4_1129.png)



![png](output_4_1130.png)



![png](output_4_1131.png)



![png](output_4_1132.png)



![png](output_4_1133.png)



![png](output_4_1134.png)



![png](output_4_1135.png)



![png](output_4_1136.png)



![png](output_4_1137.png)



![png](output_4_1138.png)



![png](output_4_1139.png)



![png](output_4_1140.png)



![png](output_4_1141.png)



![png](output_4_1142.png)



![png](output_4_1143.png)



![png](output_4_1144.png)



![png](output_4_1145.png)



![png](output_4_1146.png)



![png](output_4_1147.png)



![png](output_4_1148.png)



![png](output_4_1149.png)



![png](output_4_1150.png)



![png](output_4_1151.png)



![png](output_4_1152.png)



![png](output_4_1153.png)



![png](output_4_1154.png)



![png](output_4_1155.png)



![png](output_4_1156.png)



![png](output_4_1157.png)



![png](output_4_1158.png)



![png](output_4_1159.png)



![png](output_4_1160.png)



![png](output_4_1161.png)



![png](output_4_1162.png)



![png](output_4_1163.png)



![png](output_4_1164.png)



![png](output_4_1165.png)



![png](output_4_1166.png)



![png](output_4_1167.png)



![png](output_4_1168.png)



![png](output_4_1169.png)



![png](output_4_1170.png)



![png](output_4_1171.png)



![png](output_4_1172.png)



![png](output_4_1173.png)



![png](output_4_1174.png)



![png](output_4_1175.png)



![png](output_4_1176.png)



![png](output_4_1177.png)



![png](output_4_1178.png)



![png](output_4_1179.png)



![png](output_4_1180.png)



![png](output_4_1181.png)



![png](output_4_1182.png)



![png](output_4_1183.png)



![png](output_4_1184.png)



![png](output_4_1185.png)



![png](output_4_1186.png)



![png](output_4_1187.png)



![png](output_4_1188.png)



![png](output_4_1189.png)



![png](output_4_1190.png)



![png](output_4_1191.png)



![png](output_4_1192.png)



![png](output_4_1193.png)



![png](output_4_1194.png)



![png](output_4_1195.png)



![png](output_4_1196.png)



![png](output_4_1197.png)



![png](output_4_1198.png)



![png](output_4_1199.png)



![png](output_4_1200.png)



![png](output_4_1201.png)



![png](output_4_1202.png)



![png](output_4_1203.png)



![png](output_4_1204.png)



![png](output_4_1205.png)



![png](output_4_1206.png)



![png](output_4_1207.png)



![png](output_4_1208.png)



![png](output_4_1209.png)



![png](output_4_1210.png)



![png](output_4_1211.png)



![png](output_4_1212.png)



![png](output_4_1213.png)



![png](output_4_1214.png)



![png](output_4_1215.png)



![png](output_4_1216.png)



![png](output_4_1217.png)



![png](output_4_1218.png)



![png](output_4_1219.png)



![png](output_4_1220.png)



![png](output_4_1221.png)



![png](output_4_1222.png)



![png](output_4_1223.png)



![png](output_4_1224.png)



![png](output_4_1225.png)



![png](output_4_1226.png)



![png](output_4_1227.png)



![png](output_4_1228.png)



![png](output_4_1229.png)



![png](output_4_1230.png)



![png](output_4_1231.png)



![png](output_4_1232.png)



![png](output_4_1233.png)



![png](output_4_1234.png)



![png](output_4_1235.png)



![png](output_4_1236.png)



![png](output_4_1237.png)



![png](output_4_1238.png)



![png](output_4_1239.png)



![png](output_4_1240.png)



![png](output_4_1241.png)



![png](output_4_1242.png)



![png](output_4_1243.png)



![png](output_4_1244.png)



![png](output_4_1245.png)



![png](output_4_1246.png)



![png](output_4_1247.png)



![png](output_4_1248.png)



![png](output_4_1249.png)



![png](output_4_1250.png)



![png](output_4_1251.png)



![png](output_4_1252.png)



![png](output_4_1253.png)



![png](output_4_1254.png)



![png](output_4_1255.png)



![png](output_4_1256.png)



![png](output_4_1257.png)



![png](output_4_1258.png)



![png](output_4_1259.png)



![png](output_4_1260.png)



![png](output_4_1261.png)



![png](output_4_1262.png)



![png](output_4_1263.png)



![png](output_4_1264.png)



![png](output_4_1265.png)



![png](output_4_1266.png)



![png](output_4_1267.png)



![png](output_4_1268.png)



![png](output_4_1269.png)



![png](output_4_1270.png)



![png](output_4_1271.png)



![png](output_4_1272.png)



![png](output_4_1273.png)



![png](output_4_1274.png)



![png](output_4_1275.png)



![png](output_4_1276.png)



![png](output_4_1277.png)



![png](output_4_1278.png)



![png](output_4_1279.png)



![png](output_4_1280.png)



![png](output_4_1281.png)



![png](output_4_1282.png)



![png](output_4_1283.png)



![png](output_4_1284.png)



![png](output_4_1285.png)



![png](output_4_1286.png)



![png](output_4_1287.png)



![png](output_4_1288.png)



![png](output_4_1289.png)



![png](output_4_1290.png)



![png](output_4_1291.png)



![png](output_4_1292.png)



![png](output_4_1293.png)



![png](output_4_1294.png)



![png](output_4_1295.png)



![png](output_4_1296.png)



![png](output_4_1297.png)



![png](output_4_1298.png)



![png](output_4_1299.png)



![png](output_4_1300.png)



![png](output_4_1301.png)



![png](output_4_1302.png)



![png](output_4_1303.png)



![png](output_4_1304.png)



![png](output_4_1305.png)



![png](output_4_1306.png)



![png](output_4_1307.png)



![png](output_4_1308.png)



![png](output_4_1309.png)



![png](output_4_1310.png)



![png](output_4_1311.png)



![png](output_4_1312.png)



![png](output_4_1313.png)



![png](output_4_1314.png)



![png](output_4_1315.png)



![png](output_4_1316.png)



![png](output_4_1317.png)



![png](output_4_1318.png)



![png](output_4_1319.png)



![png](output_4_1320.png)



![png](output_4_1321.png)



![png](output_4_1322.png)



![png](output_4_1323.png)



![png](output_4_1324.png)



![png](output_4_1325.png)



![png](output_4_1326.png)



![png](output_4_1327.png)



![png](output_4_1328.png)



![png](output_4_1329.png)



![png](output_4_1330.png)



![png](output_4_1331.png)



![png](output_4_1332.png)



![png](output_4_1333.png)



![png](output_4_1334.png)



![png](output_4_1335.png)



![png](output_4_1336.png)



![png](output_4_1337.png)



![png](output_4_1338.png)



![png](output_4_1339.png)



![png](output_4_1340.png)



![png](output_4_1341.png)



![png](output_4_1342.png)



![png](output_4_1343.png)



![png](output_4_1344.png)



![png](output_4_1345.png)



![png](output_4_1346.png)



![png](output_4_1347.png)



![png](output_4_1348.png)



![png](output_4_1349.png)



![png](output_4_1350.png)



![png](output_4_1351.png)



![png](output_4_1352.png)



![png](output_4_1353.png)



![png](output_4_1354.png)



![png](output_4_1355.png)



![png](output_4_1356.png)



![png](output_4_1357.png)



![png](output_4_1358.png)



![png](output_4_1359.png)



![png](output_4_1360.png)



![png](output_4_1361.png)



![png](output_4_1362.png)



![png](output_4_1363.png)



![png](output_4_1364.png)



![png](output_4_1365.png)



![png](output_4_1366.png)



![png](output_4_1367.png)



![png](output_4_1368.png)



![png](output_4_1369.png)



![png](output_4_1370.png)



![png](output_4_1371.png)



![png](output_4_1372.png)



![png](output_4_1373.png)



![png](output_4_1374.png)



![png](output_4_1375.png)



![png](output_4_1376.png)



![png](output_4_1377.png)



![png](output_4_1378.png)



![png](output_4_1379.png)



![png](output_4_1380.png)



![png](output_4_1381.png)



![png](output_4_1382.png)



![png](output_4_1383.png)



![png](output_4_1384.png)



![png](output_4_1385.png)



![png](output_4_1386.png)



![png](output_4_1387.png)



![png](output_4_1388.png)



![png](output_4_1389.png)



![png](output_4_1390.png)



![png](output_4_1391.png)



![png](output_4_1392.png)



![png](output_4_1393.png)



![png](output_4_1394.png)



![png](output_4_1395.png)



![png](output_4_1396.png)



![png](output_4_1397.png)



![png](output_4_1398.png)



![png](output_4_1399.png)



![png](output_4_1400.png)



![png](output_4_1401.png)



![png](output_4_1402.png)



![png](output_4_1403.png)



![png](output_4_1404.png)



![png](output_4_1405.png)



![png](output_4_1406.png)



![png](output_4_1407.png)



![png](output_4_1408.png)



![png](output_4_1409.png)



![png](output_4_1410.png)



![png](output_4_1411.png)



![png](output_4_1412.png)



![png](output_4_1413.png)



![png](output_4_1414.png)



![png](output_4_1415.png)



![png](output_4_1416.png)



![png](output_4_1417.png)



![png](output_4_1418.png)



![png](output_4_1419.png)



![png](output_4_1420.png)



![png](output_4_1421.png)



![png](output_4_1422.png)



![png](output_4_1423.png)



![png](output_4_1424.png)



![png](output_4_1425.png)



![png](output_4_1426.png)



![png](output_4_1427.png)



![png](output_4_1428.png)



![png](output_4_1429.png)



![png](output_4_1430.png)



![png](output_4_1431.png)



![png](output_4_1432.png)



![png](output_4_1433.png)



![png](output_4_1434.png)



![png](output_4_1435.png)



![png](output_4_1436.png)



![png](output_4_1437.png)



![png](output_4_1438.png)



![png](output_4_1439.png)



![png](output_4_1440.png)



![png](output_4_1441.png)



![png](output_4_1442.png)



![png](output_4_1443.png)



![png](output_4_1444.png)



![png](output_4_1445.png)



![png](output_4_1446.png)



![png](output_4_1447.png)



![png](output_4_1448.png)



![png](output_4_1449.png)



![png](output_4_1450.png)



![png](output_4_1451.png)



![png](output_4_1452.png)



![png](output_4_1453.png)



![png](output_4_1454.png)



![png](output_4_1455.png)



![png](output_4_1456.png)



![png](output_4_1457.png)



![png](output_4_1458.png)



![png](output_4_1459.png)



![png](output_4_1460.png)



![png](output_4_1461.png)



![png](output_4_1462.png)



![png](output_4_1463.png)



![png](output_4_1464.png)



![png](output_4_1465.png)



![png](output_4_1466.png)



![png](output_4_1467.png)



![png](output_4_1468.png)



![png](output_4_1469.png)



![png](output_4_1470.png)



![png](output_4_1471.png)



![png](output_4_1472.png)



![png](output_4_1473.png)



![png](output_4_1474.png)



![png](output_4_1475.png)



![png](output_4_1476.png)



![png](output_4_1477.png)



![png](output_4_1478.png)



![png](output_4_1479.png)



![png](output_4_1480.png)



![png](output_4_1481.png)



![png](output_4_1482.png)



![png](output_4_1483.png)



![png](output_4_1484.png)



![png](output_4_1485.png)



![png](output_4_1486.png)



![png](output_4_1487.png)



![png](output_4_1488.png)



![png](output_4_1489.png)



![png](output_4_1490.png)



![png](output_4_1491.png)



![png](output_4_1492.png)



![png](output_4_1493.png)



![png](output_4_1494.png)



![png](output_4_1495.png)



![png](output_4_1496.png)



![png](output_4_1497.png)



![png](output_4_1498.png)



![png](output_4_1499.png)



![png](output_4_1500.png)



![png](output_4_1501.png)



![png](output_4_1502.png)



```python
last = 1
non = 1
for key in unique.keys():
    btc = list()
    for item in unique[key]:
        if item != 0:
            if item == last:
                btc.append(non)
            else:
                non = item / last
                if (non != float('inf')) and (non != float('NaN')):
                    btc.append(non)
                else:
                    btc.append(1)
            last = item
    #print(btc)
    print(key + " mean: " + str(np.mean(btc)) + " median: " + str(np.median(btc)) + " var: " + str(np.var(btc)))
    #if key == 'BTC':
    #    print(btc[6:])

```

    BTC mean: 1.452912854772651 median: 1.0060323927759613 var: 61.6871063816049
    ETH mean: 1.142519053587995 median: 0.998232862096559 var: 1.6071485971972739
    XRP mean: 1.3017321490850111 median: 0.9853151762752137 var: 12.373601442510884
    BCH mean: 12.945640884054608 median: 0.9668998658409952 var: 6219.93187291362
    LTC mean: 1.1148745418505308 median: 0.9891598915989159 var: 1.3729988955466232
    ADA mean: 1.190923423744155 median: 0.9699758537978983 var: 0.7178219505581185
    NEO mean: 3.092732957381206 median: 0.9844236823788952 var: 369.6727603569152
    XLM mean: 1.1021693112394944 median: 0.9783121169259783 var: 0.8165802260063808
    XMR mean: 1.175528686275709 median: 0.9854368932038834 var: 2.465980534148855
    EOS mean: 1.0295643706057975 median: 0.9715714129299131 var: 0.12317524699468399
    MIOTA mean: 1.044410549522482 median: 0.9785202863961812 var: 0.10231362448108122
    DASH mean: 1.1066978661053206 median: 0.9873284054910242 var: 0.4756157339575706
    XEM mean: 1.2352191405066308 median: 1.0027974044700794 var: 3.1874979446413354
    TRX mean: 1.316752474976317 median: 0.9745872248165443 var: 2.0530690647382004
    ETC mean: 1.4485107637980383 median: 0.992 var: 6.324618857426571
    VEN mean: 1.1221573397244786 median: 0.958097789149642 var: 0.2355774111461405
    USDT mean: 1.2083326770967693 median: 1.0273015664294285 var: 0.09721078127735981
    QTUM mean: 1.1813573178852825 median: 0.9686274509803922 var: 0.7304490153335792
    NANO mean: 10.930231183121819 median: 1.009891676168757 var: 6270.504985436925
    LSK mean: 2.6919203759288806 median: 0.9796387672737125 var: 308.9056674096787
    BTG mean: 2.82695507602521 median: 0.9647573678028653 var: 296.8724580234772
    OMG mean: 1.0810497585889776 median: 1.008130081300813 var: 0.1180926926340359
    ICX mean: 1.0977553115811667 median: 1.0122699386503067 var: 0.2009707149247079
    ZEC mean: 6.511714784305361 median: 0.9769506895900246 var: 2812.119814278359
    DGD mean: 1.0909047078765102 median: 1.0178217821782178 var: 0.6050632958955177
    BNB mean: 1.1852152815465014 median: 1.0208333333333333 var: 0.4542550539540464
    STEEM mean: 1.3106607939755108 median: 0.9482357629034488 var: 4.68525094893172
    XVG mean: 1.8380569776699784 median: 0.9722222222222221 var: 127.54008517397178
    STRAT mean: 1.6803568933728767 median: 1.025 var: 40.965898710098244
    BCN mean: 1.375480666213529 median: 0.9838709677419354 var: 17.25932094729135
    PPT mean: 21.314896013500928 median: 1.0265957446808511 var: 15738.807724774055
    WAVES mean: 1.589878423165283 median: 0.9955820250888965 var: 28.95883237132463
    SNT mean: 1.0906323567372842 median: 0.9909156182686605 var: 0.37314824905406974
    SC mean: 1.6165604862633904 median: 0.9729319504174045 var: 28.558527170972614
    WTC mean: 2.564796692325069 median: 1.0321969696969697 var: 74.51838142871652
    MKR mean: 1.350799830391338 median: 0.893037075313267 var: 4.3245784594297625
    RHOC mean: 1.1223720382694338 median: 1.0042194092827004 var: 0.41772615374649696
    DOGE mean: 1.0498659812592537 median: 0.9857819905213272 var: 0.2795743398531849
    DCR mean: 11.458554194927792 median: 0.9956368820229575 var: 3630.9288276703214
    BTS mean: 1.8199618434287803 median: 0.9857384015367601 var: 106.8464187038999
    AE mean: 1.148189645928654 median: 0.9750061265816252 var: 0.48694039508005516
    REP mean: 1.0859574081360037 median: 1.0125742228431716 var: 0.235840552784105
    BTM mean: 1.0937403737786944 median: 0.9703051714685997 var: 0.3468145560986367
    KMD mean: 1.335338668883633 median: 1.044642857142857 var: 5.836787224459686
    ZRX mean: 1.0366246779858221 median: 0.989745242907925 var: 0.0948082380499363
    ETN mean: 1.0586070699963275 median: 0.9931159280295715 var: 0.26050578605843927
    VERI mean: 13.558480636565426 median: 0.9663767199114345 var: 8238.644880087371
    ARK mean: 1.0921854900972023 median: 1.0066037735849056 var: 0.1551049809508172
    ARDR mean: 1.0619895569768474 median: 0.9877926978137833 var: 0.5018233167540916
    HSR mean: 2.2274586688079543 median: 0.967237163814181 var: 55.81849629628127
    GNT mean: 1.4140273499993008 median: 1.0012983756282787 var: 7.563446700506783
    DRGN mean: 1.1647398847431498 median: 0.9455445544554455 var: 0.24679137657711517
    SYS mean: 1.1878352282746694 median: 0.9981412639405204 var: 2.3640591399366238
    BAT mean: 208.6812194496848 median: 0.975 var: 8584781.201097142
    GAS mean: 1.2452853417038463 median: 1.011204481792717 var: 0.7616172288356529
    ETHOS mean: 1.1556920648932587 median: 0.9854464812035941 var: 0.3017707901530974
    CNX mean: 1.0238567175259727 median: 1.0162271805273835 var: 0.058678923427166775
    DGB mean: 2.054061630608091 median: 0.9728228760486823 var: 168.65230605374188
    ZIL mean: 1.34908925122346 median: 0.9526803544682976 var: 1.680609282030191
    PIVX mean: 1.5527536845539345 median: 1.014219576719577 var: 21.767764314950035
    KCS mean: 1.1042769534364971 median: 0.8971060821467634 var: 0.2764958417477779
    MONA mean: 1.2848901567627764 median: 0.9823940179224943 var: 15.643118935477192
    AION mean: 1.0897418104403978 median: 1.0233392776805146 var: 0.21484952285937076
    ELF mean: 1.003857553136716 median: 0.913793103448276 var: 0.1268343632841121
    GBYTE mean: 1.2432369282639386 median: 1.0257332402234636 var: 1.3414610641359583
    QASH mean: 0.9979598375513752 median: 0.9821647679895743 var: 0.1486150930964234
    PART mean: 1.2433659717026444 median: 0.9970990468296725 var: 1.534316037535248
    LRC mean: 1.1150692670869953 median: 0.9741379310344828 var: 0.28434033294430494
    FCT mean: 1.114712718217053 median: 0.992619926199262 var: 0.5259334513940901
    FUN mean: 1.0180349680111023 median: 0.968480779513992 var: 0.1281884534650867
    NAS mean: 3.0582681740686986 median: 0.924914675767918 var: 157.12105505905367
    KNC mean: 3.617186423629299 median: 0.9951048951048951 var: 26.623508309558687
    R mean: 1.1524252308075127 median: 1.062015503875969 var: 0.2044763363843943
    RDD mean: 1.334311314775226 median: 0.9761904761904763 var: 15.960009401862312
    KIN mean: 1.104473812895228 median: 0.9859154929577465 var: 0.28684028114907145
    IOST mean: 18.342800815202 median: 0.8485453508271535 var: 2319.5128208371084
    GXS mean: 4.581965668564756 median: 0.954305799648506 var: 613.2570664926641
    SALT mean: 1.0355503264083596 median: 0.976923076923077 var: 0.07280334923039689
    XZC mean: 1.1728437530584854 median: 1.0325814536340852 var: 0.6155956337393188
    DENT mean: 1.2509894137174897 median: 1.0174741262936853 var: 1.2898956293084918
    NEBL mean: 2.5047484521448684 median: 0.9906542056074766 var: 57.01551050831391
    LINK mean: 1.0491299248175354 median: 0.9539389933871327 var: 0.13774579289143293
    BLOCK mean: 1.3437055625382635 median: 0.9898364429171193 var: 17.753834353335378
    POLY mean: 0.8565574076687121 median: 0.9279260885100301 var: 0.23854514238837804
    POWR mean: 1.112612009555885 median: 0.9639639639639639 var: 0.26779500720057314
    DCN mean: 1.326798107650677 median: 0.9252873563218391 var: 4.9943757458446925
    ICN mean: 43.10127174519086 median: 1.0118522925653088 var: 47830.43183767896
    BNT mean: 19.155813962759957 median: 0.9912109375 var: 16815.518383662577
    NXS mean: 1.388629457911691 median: 1.0038192234245702 var: 7.1731177227538785
    NXT mean: 1.152671717381842 median: 0.9756705385427666 var: 2.5472290690462387
    PAY mean: 6.146385822557595 median: 0.942597791502901 var: 1282.2801654582142
    ENG mean: 1.0699211649525524 median: 0.9978678038379529 var: 0.12311354186014048
    REQ mean: 1.0920994866147324 median: 0.957889969889274 var: 0.24560085038825746
    SMART mean: 1.1683150353227703 median: 0.9189182032721341 var: 0.6326776702503388
    CND mean: 1.1151227330749591 median: 0.9398770896901456 var: 0.28566193641891874
    MAID mean: 1.027691705044405 median: 1.005011812712232 var: 0.05568089616779572
    EMC mean: 1.0794859613768686 median: 1.0072271129428403 var: 0.15066323594340253
    PLR mean: 1.0884202197059045 median: 1.0156375971645446 var: 0.1619363685403388
    AGI mean: 0.9871527523406866 median: 0.8769113715918289 var: 0.17941912857054648
    SRN mean: 1.1368722775356725 median: 0.9318181818181818 var: 0.3407734410265386
    STORJ mean: 1.0764063435534883 median: 0.9333333333333332 var: 0.30530976629916834
    GNO mean: 2.3911746605278528 median: 0.9900113205034294 var: 110.40881802337397
    VTC mean: 1.150272687198578 median: 0.9652163864332352 var: 2.71427716757932
    GAME mean: 1.4009935006686063 median: 0.989974028853986 var: 3.5414527053781675
    WAX mean: 0.9909324533494138 median: 0.7857142857142858 var: 0.31651141172830943
    GVT mean: 1.6283493763361325 median: 1.0628930817610063 var: 4.205612615332266
    BTCD mean: 1.1490149406204286 median: 0.9965517241379311 var: 1.9559451179953495
    QSP mean: 1.0155469004641327 median: 0.9645842887445937 var: 0.16675311509906532
    RDN mean: 1.3296679708009278 median: 1.0436046511627908 var: 1.7654755056424845
    ENJ mean: 1.115384775074554 median: 0.9865561982179146 var: 0.22473339799406505
    BTX mean: 1.489635232542469 median: 0.9932665994526861 var: 10.972593567755956
    MTL mean: 1.0063176873302873 median: 1.0092226613965745 var: 0.05285085015526964
    ANT mean: 1.029140950593453 median: 0.9915534775783224 var: 0.0611073763484333
    THETA mean: 0.9676789635499783 median: 0.9486195703709107 var: 0.24676722779388843
    IGNIS mean: 1.634858356510711 median: 0.8961626373322837 var: 5.379707733026168
    ZEN mean: 2.2317771903997587 median: 0.9753896636587368 var: 74.021916168667
    SAN mean: 1.0780557411052578 median: 0.9738499328999095 var: 0.1961368019191068
    CVC mean: 1.0236363529433363 median: 1.0190130191306537 var: 0.07835993909156126
    UBQ mean: 1.4397229336873414 median: 1.0197254335260115 var: 16.190998183072296
    SKY mean: 1.0608898842333034 median: 1.017948717948718 var: 0.10248862456423186
    MANA mean: 1.109006910394537 median: 1.0010152995133565 var: 0.6132174959651278
    UNITY mean: 1.3876329347928373 median: 0.9865319865319865 var: 12.025998485115213
    MCO mean: 1.0637286044515517 median: 1.0139211136890953 var: 0.20574008165896174
    PURA mean: 152.93852385452323 median: 0.96 var: 4520504.212905081
    NAV mean: 1.2230530548890828 median: 0.9928893835404689 var: 2.5444310367585987
    STORM mean: 1.0308399041919534 median: 0.910313692637066 var: 0.2938540370758341
    XDN mean: 1.228125378192408 median: 0.9701492537313434 var: 4.168783746271648
    DTR mean: 1.2026791866141922 median: 1.0093597432139614 var: 0.2823098138129871
    SUB mean: 1.1646766693132722 median: 1.0091754033303542 var: 0.3980704763930259
    POE mean: 1.0980936445848197 median: 0.9330066899086027 var: 0.34911407105762327
    CS mean: 14.281121906124088 median: 14.281121906124088 var: 0.0
    NULS mean: 1.3021494585214597 median: 1.0649895178197066 var: 1.5202053144667917
    RLC mean: 1.03914726347054 median: 1.007428720287314 var: 0.09821483730072277
    MNX mean: 1.2200278934699746 median: 1.0994208494208495 var: 0.2725678778479272
    ABT mean: 0.5827685978334711 median: 0.9844961240310077 var: 0.21518000707305665
    PPP mean: 1.0911410527537029 median: 0.9655157028480776 var: 0.24138890037448696
    MDS mean: 1.1525677771217615 median: 1.0317008890906298 var: 0.5576142517242102
    TNB mean: 1.0622202515790278 median: 0.9232761657042375 var: 0.2516253431001547
    ACT mean: 1.0463877772752757 median: 0.9727070075508478 var: 0.5357637024365585
    SPHTX mean: 1.0476276624441578 median: 1.0603075892568306 var: 0.06775919757279396
    HPB mean: 2.0190781570675393 median: 0.9667194928684628 var: 10.66721495407474
    VEE mean: 1.1038306457139273 median: 0.9439764222776923 var: 0.3441703791369264
    XPA mean: 1.0765606142153246 median: 1.016053465619402 var: 0.14222758927954496
    XAS mean: 1.1479079701741222 median: 1.006800374513379 var: 0.4017014465689119
    MED mean: 1.1294122280142365 median: 0.8113927976121252 var: 0.7562117312813283
    FSN mean: 44.55887536293831 median: 0.9122340425531916 var: 3048.0468776805565
    PRL mean: 1.9361342997107154 median: 0.8557433628318585 var: 11.234074446727004
    OST mean: 1.011053127771783 median: 0.9767790287167235 var: 0.1815654496873283
    ADX mean: 1.1286552785330615 median: 0.9950663663438398 var: 0.4105627315262421
    LEND mean: 1.1250259508324933 median: 0.9570503036577687 var: 0.31632521792103396
    BCO mean: 1.2796649427739897 median: 1.0286396181384245 var: 0.44768723606665767
    TEL mean: 0.8145896135053642 median: 0.8857266999782749 var: 0.09991709818193267
    RPX mean: 1.6847488738660832 median: 1.0542908501250738 var: 7.23664617649012
    SLS mean: 1.6834165820847604 median: 1.0118032786885245 var: 18.97108920898447
    DEW mean: 0.8522868353821444 median: 0.8695803493742053 var: 0.06865002755085639
    ITC mean: 1.12047600191348 median: 1.0661764705882353 var: 0.14090993727184714
    BLZ mean: 3.6141530730350038 median: 1.5 var: 943.9572472450831
    AMB mean: 8.728843069930699 median: 1.022862348108554 var: 1476.2736145858364
    XP mean: 2.6897650724598927 median: 0.8666666666666667 var: 119.12911378378226
    C20 mean: 966.3082168242299 median: 1.003048780487805 var: 6150909.779488919
    LBC mean: 1.4788492200444123 median: 0.9595084523135741 var: 13.539734695177012
    EDG mean: 1.0585135785206903 median: 1.0222384904258741 var: 0.0769033344922781
    BAY mean: 1.3086138222505495 median: 0.9890710382513661 var: 8.121876398425654
    AGRS mean: 1.0504585237388664 median: 1.006793428769169 var: 0.1137291948122737
    CLOAK mean: 1.2214674787244797 median: 0.9876190448393715 var: 2.897671220556559
    POA mean: 0.08446738437968897 median: 0.070289281886388 var: 0.008643799383353535
    ION mean: 1.2425297189111058 median: 0.9912280701754386 var: 1.9282989827445047
    QRL mean: 1.0239616282264825 median: 1.0166878575969487 var: 0.07657335572650202
    RCN mean: 33.9014613754312 median: 0.9807692307692307 var: 53286.18148867279
    DTA mean: 19.98386168500667 median: 0.8125047568308091 var: 2757.8860923405477
    MLN mean: 32.714925429622916 median: 0.9864639733444397 var: 71770.39113960539
    BIX mean: 1.1514074589104513 median: 0.9635036496350364 var: 1.3762904093703225
    EDO mean: 1.1049349802616348 median: 1.0787671232876712 var: 0.24126802702481998
    DBC mean: 0.9196714347014904 median: 0.8707557015179317 var: 0.19156859981984126
    SPANK mean: 1.1097797565623204 median: 0.9995339144636741 var: 0.2409597825485227
    PPC mean: 1.0440845083158126 median: 0.9788172026977998 var: 0.13954451847521068
    VIBE mean: 1.15693932129955 median: 1.0443682387046596 var: 0.44364715627649576
    JNT mean: 1.0472487097750334 median: 1.1160884458009572 var: 0.013618742939967265
    INK mean: 0.9898926963344865 median: 0.8797656949777845 var: 0.07828666354700506
    SNM mean: 1.0803365827302285 median: 0.9805063644443139 var: 0.21730322021925458
    WINGS mean: 1.2465371971110921 median: 0.9793453041460709 var: 1.7104997081590076
    BURST mean: 1.3487222761171573 median: 0.9868746139592339 var: 17.082524107767263
    WGR mean: 1.0876522399388637 median: 1.0522522208066456 var: 0.1003404484076455
    SPC mean: 0.9283430715380142 median: 0.9317277850244495 var: 0.050516849700376155
    EMC2 mean: 1.6802749413946025 median: 0.9806315660452519 var: 51.012574353784316
    EVN mean: 1.8576998231060857 median: 1.1975964853010042 var: 2.128039140696628
    CMT mean: 1.263414705873814 median: 0.9547326111465125 var: 1.5708001780573373
    MGO mean: 1.2858772500931461 median: 0.9615384615384615 var: 4.001486210416035
    UTNP mean: 0.6319631918576908 median: 0.7733116622228715 var: 0.14524378935613375
    DATA mean: 1.0942790250714118 median: 0.9627954240010489 var: 0.14037749434971578
    SNGLS mean: 1.1126978390385982 median: 0.9920979447873567 var: 0.740283419151777
    AST mean: 1.1337610160309683 median: 1.032423433554372 var: 0.2750682318305976
    COB mean: 1.146981503032062 median: 1.0270451460993837 var: 0.9026648881703201
    APPC mean: 3.144553060008826 median: 0.8421052631578947 var: 51.63258070005748
    UTK mean: 1.1169067761713534 median: 0.930044216626837 var: 0.913978979094278
    BRD mean: 1.5463505514795524 median: 0.9178056074766355 var: 4.550091751543403
    WPR mean: 0.9129852500719228 median: 1.0605027170874612 var: 0.21062416035865056
    VIA mean: 1.3741758784965712 median: 0.9975014104940759 var: 13.677243496160797
    XBY mean: 1.1716567734253873 median: 1.0231836642599277 var: 0.4127421681046337
    HTML mean: 1.0451672082422285 median: 0.9514348785871963 var: 0.37136592033548
    ETP mean: 108.4047008481123 median: 0.9732620320855615 var: 612773.7619692951
    WABI mean: 1.0792569441865272 median: 0.9806451612903225 var: 0.11795894476074538
    NLG mean: 1.0572686961524371 median: 0.9931071049840933 var: 0.16321572533352532
    INS mean: 6.521122989730423 median: 0.9073359073359074 var: 297.0812308711226
    XCP mean: 1.105687164954634 median: 0.9832214765100672 var: 0.6358695624321009
    GTO mean: 0.9843956945108995 median: 0.8930691948374327 var: 0.21242970913418294
    DPY mean: 1.1314303911850365 median: 0.98640851892436 var: 0.1576112412555153
    TAAS mean: 1.036608222243282 median: 1.040268456375839 var: 0.03516746980419849
    AEON mean: 1.1508863346368148 median: 0.9825897934734957 var: 0.8074186983266689
    RISE mean: 2.2918174027732805 median: 0.9836065573770492 var: 124.73635761674045
    TRAC mean: 0.9594331514043869 median: 0.9275096309892308 var: 0.14326839625940882
    FUEL mean: 1.0743270482714562 median: 1.0614725477983504 var: 0.19837826423933405
    HST mean: 1.2717119193187387 median: 0.9142876933765218 var: 0.5168902687807089
    NGC mean: 0.9784681911859002 median: 1.010810810810811 var: 0.03140737647262056
    FTC mean: 1.0890067518871287 median: 0.9553784860557768 var: 0.6382791561764857
    MOBI mean: 0.9882658983823643 median: 0.7803857773646292 var: 0.14147638605917187
    DNT mean: 1.110570860252219 median: 0.9753028028542639 var: 0.31522847635611956
    CPC mean: 1.0916336875680235 median: 0.9932823071413996 var: 0.21927463892345708
    TNC mean: 0.8833944888797646 median: 0.8182654278644338 var: 0.05701907066324707
    MOD mean: 1.370020702499873 median: 1.0264550264550265 var: 2.2935874760228505
    AMP mean: 1.1250318808014772 median: 1.0078953801026642 var: 0.42119796708296703
    GRS mean: 1.1449976217315716 median: 0.9722222222222222 var: 2.095334040755911
    ADT mean: 1.034910188301047 median: 0.9887588215890736 var: 0.1428892858781249
    UKG mean: 1.105503110175389 median: 0.9918890600617716 var: 0.1858521864690906
    BTO mean: 0.9479639412966199 median: 0.9847237009307277 var: 0.03107151117686606
    LUN mean: 1.363378071790814 median: 1.0059880239520957 var: 3.7628179049833324
    CRW mean: 1.4959675356310826 median: 0.9668633681343621 var: 12.774947923400601
    CFI mean: 1.0033595856997268 median: 0.9094867995282305 var: 0.12220918163448606
    BCPT mean: 1.183875289303861 median: 0.9643131390696359 var: 0.38152617021005947
    TNT mean: 0.9925714306172593 median: 0.8794693166683742 var: 0.10804533416467996
    ZCL mean: 1.6738577895290687 median: 0.973293768545994 var: 21.283488401286203
    DCT mean: 1.4095112674300632 median: 1.0010936687805385 var: 8.151634086847709
    TRIG mean: 2.1416446060714027 median: 0.9954228706975523 var: 95.86461081759171
    SHIFT mean: 1.4323495877854437 median: 0.9734251147267419 var: 10.430041470218034
    CTR mean: 1.0921678829886585 median: 0.9119852883115406 var: 0.3125327252847121
    HMQ mean: 1.0516026630395092 median: 0.9917911929852012 var: 0.1483517822117743
    UCASH mean: 0.7274661183591491 median: 0.7565508191169623 var: 0.07755678443768588
    CDT mean: 1.1094743593242473 median: 1.0154667340070531 var: 0.41570799719215135
    MTN mean: 2.0725638666214588 median: 1.4501519187059182 var: 1.364545880837154
    VIB mean: 1.0649690663906943 median: 1.0243449097661934 var: 0.15505514038459461
    FLASH mean: 1.089290114155771 median: 1.0078891668270156 var: 0.42545952210979254
    IDH mean: 1.6152998013074815 median: 0.7850205670430389 var: 2.6126249723087027
    TKN mean: 1.2078789310193674 median: 0.9846153846153846 var: 1.688117069540333
    HVN mean: 1.0431707097564757 median: 0.9489540459116561 var: 0.1574215164216959
    ECC mean: 1.8943629044192896 median: 0.9500000000000001 var: 42.63564670862349
    SIB mean: 1.112690242248761 median: 0.9948186528497409 var: 0.2942244915184383
    DAT mean: 0.9787529591917148 median: 0.9777461109131932 var: 0.15127225295966865
    CRPT mean: 8.148155155088578 median: 0.8485311365761654 var: 375.2903225619359
    IOC mean: 1.0902882924860813 median: 0.9944887078416101 var: 0.4551429385821577
    SAFEX mean: 1.2860986024696732 median: 0.9725421401876286 var: 4.0139296403753
    PRE mean: 1.6485952457032917 median: 0.9138287696214378 var: 4.36849202113396
    SBD mean: 1.0783512870915088 median: 1.0085474601610651 var: 0.2878972708912349
    QLC mean: 0.9485541832802834 median: 0.9753364250511608 var: 0.21359332143467288
    KICK mean: 1.0531848599292513 median: 0.9212336640316904 var: 0.40901065032439227
    OCN mean: 1.0354114750347443 median: 0.756815142528412 var: 0.6865455469064352
    BITCNY mean: 1.0934427024154814 median: 0.9984515188778065 var: 0.6013104326795126
    ATM mean: 1.1076800722754352 median: 0.9122071986288327 var: 0.6440881111003747
    POT mean: 1.175708788070864 median: 0.987467552404611 var: 2.285200029826717
    UNO mean: 1.6530272380329718 median: 0.9866220735785953 var: 52.37983625221747
    PEPECASH mean: 1.1848684667818352 median: 0.9767441860465115 var: 0.5474015378383811
    SXDT mean: 3.2015771888874025 median: 1.024985788958555 var: 45.26678208275757
    BLT mean: 1.2698036473735288 median: 0.8899635142840492 var: 1.2554085325574187
    XWC mean: 3.6915837364360433 median: 0.980327868852459 var: 1802.9441692647413
    NMR mean: 25.764434059871068 median: 0.9716461013389339 var: 30439.629434485814
    MER mean: 1.2339796340364528 median: 1.0025858884373846 var: 1.1784706664748807
    NMC mean: 1.0616190578626346 median: 0.9797640384645356 var: 0.32472877342139184
    COSS mean: 1.156928117774967 median: 0.9957950786513621 var: 0.36779900614350564
    EVX mean: 1.1658766343474927 median: 0.9513513513513513 var: 0.41942387733931974
    BITB mean: 2.002826825201785 median: 0.9841269841269842 var: 86.01774180780212
    BPT mean: 8.065248704816979 median: 1.0746447307282692 var: 301.77661010558444
    COLX mean: 1.3516262418264078 median: 1.018181818181818 var: 2.2747061600326917
    GRID mean: 9.800067968318258 median: 0.9997809844416725 var: 1774.2764236503697
    SWM mean: 0.9056562041456311 median: 0.7457072848831799 var: 0.20400877336078518
    BLK mean: 1.1907699959279292 median: 0.993003110299977 var: 3.7113783042746213
    VOX mean: 1.3602757001998262 median: 0.9514696261509347 var: 11.880317678994672
    ORME mean: 1.2523039737757655 median: 0.9706462377333496 var: 1.0715564323256461
    DMD mean: 1.1173728124358366 median: 0.9940768877210326 var: 1.841206688522422
    ONION mean: 1.1129101499750709 median: 0.9528181869242867 var: 0.27562176997770355
    VRC mean: 1.2035523759444202 median: 0.979184082929276 var: 3.631062202872843
    LET mean: 0.8145897285489344 median: 0.8804692929265401 var: 0.09081347060752169
    CAPP mean: 1.1954560705848536 median: 0.9291217594339365 var: 0.5254710676162178
    MINT mean: 1.1574025620923099 median: 0.9756097560975611 var: 2.1670229077444105
    INT mean: 43.196422545186095 median: 0.8989308895594036 var: 15350.463228710045
    SOAR mean: 1.0265167006225788 median: 1.0157215945427414 var: 0.14554227189203137
    TRST mean: 1.080159407226851 median: 1.0370710494685806 var: 0.1147700379570828
    STK mean: 0.821988334172896 median: 0.774388329899496 var: 0.3076576648207451
    NET mean: 97.77489959755798 median: 0.9547738693467335 var: 202686.79156718528
    XEL mean: 6.091654033911787 median: 1.0074091253459498 var: 1263.9390185126504
    XTO mean: 1.2035934276335332 median: 1.024216984178237 var: 1.2786488930350246
    SNC mean: 1.1678257413487743 median: 0.9226967632489127 var: 1.1119122458834
    SOC mean: 0.879745491051773 median: 0.7696159635706235 var: 0.05025142953704265
    ZSC mean: 1.0017095329341765 median: 1.0006484633733992 var: 0.11160930504680296
    LKK mean: 1.1104295462026479 median: 0.9976136366951495 var: 0.438074041876966
    DADI mean: 1.9572184109566926 median: 2.05493480590469 var: 0.825622814801193
    1ST mean: 1.180946943986367 median: 0.9736851969830631 var: 2.06149298368336
    MTH mean: 1.0220503395574256 median: 0.8949582838127272 var: 0.12107920886678655
    ZAP mean: 1.4110790668766038 median: 0.8402813488193398 var: 2.835274553462648
    ZOI mean: 11.68415014897425 median: 0.9483079314844118 var: 6828.705326620113
    TAU mean: 0.832858316630198 median: 0.83977482838899 var: 0.022626206578503155
    GUP mean: 1.0625990733215431 median: 0.9799666855052204 var: 0.19096404819367258
    YOYOW mean: 1.0731954831653936 median: 0.9400927837816093 var: 0.3112593761054991
    LEO mean: 1.0448682788421915 median: 0.9824435416038471 var: 0.16511537775972113
    ARN mean: 1.231880193572492 median: 1.0321048632218845 var: 0.5478352317143969
    EXP mean: 1.1756247005537426 median: 0.9764150943396225 var: 1.515364532530093
    QBT mean: 5.032530554999002 median: 0.951048951048951 var: 565.5300966464025
    GRC mean: 1.1449345951124854 median: 0.9913424221315555 var: 1.6017607145143424
    FAIR mean: 1.1474437265799298 median: 1.0034163326982457 var: 2.3541346997911465
    HMC mean: 1.5385364983126983 median: 0.960228148604902 var: 6.869701155282142
    MSP mean: 1.2373370034487818 median: 1.0154687688533162 var: 1.410489296671986
    ZPT mean: 0.959661104324976 median: 0.879261003665313 var: 0.07784489108049128
    SWFTC mean: 0.8703516034827807 median: 0.8268511442706029 var: 0.07330203114541833
    AURA mean: 4.861811580648093 median: 0.9964430228525184 var: 111.21538672290903
    UQC mean: 1.6280438601386311 median: 1.0159371053520927 var: 5.341845370440916
    EVR mean: 0.9944727906657199 median: 0.904961438972474 var: 0.12447701034450072
    MOON mean: 1.731412682204631 median: 0.9411764705882354 var: 50.04476743743493
    KEY mean: 38.42692506465368 median: 0.8161283709488044 var: 12149.44672893014
    TSL mean: 1.3444063271747735 median: 0.9407470139882603 var: 2.1667370099024947
    IFT mean: 1.062973329261605 median: 0.9661079298125145 var: 0.13040110165189842
    ART mean: 1.1609293572480373 median: 1.0306138495442918 var: 0.24014166889083619
    DIME mean: 1.3689680416419654 median: 0.9411764705882354 var: 5.810019070864071
    TIME mean: 14514.81966111482 median: 1.0236034618410699 var: 1734176434.6041481
    TIX mean: 1.0913665309896137 median: 0.9242795552954346 var: 0.3392677975900876
    NLC2 mean: 5.306605323254434 median: 0.9859154929577466 var: 1801.7348163274623
    GTC mean: 1.0823240485831922 median: 0.9275726558216049 var: 0.490084370389278
    BCC mean: 3.575061311455849 median: 1.0322974233833346 var: 215.1904715568279
    MDA mean: 1.181897933046876 median: 0.9295154185022025 var: 1.4936907209634263
    DLT mean: 1.0254831360473937 median: 0.9847408695182203 var: 0.13221753423267812
    CHSB mean: 0.7281544377089723 median: 0.8417236979468739 var: 0.05945393842048015
    ECA mean: 1.722373653369134 median: 0.9183673469387754 var: 4.270043359544239
    QUN mean: 12.535830730460555 median: 0.9258718974864026 var: 1214.1510818979243
    TIO mean: 3.777053499558803 median: 0.8496334118879286 var: 78.65549016373585
    BMC mean: 1.0853011342089165 median: 1.0070626428509872 var: 0.1279689245707646
    POSW mean: 1.5775481528641615 median: 0.9885807504078304 var: 9.420759524778516
    OMNI mean: 1.7729066852850786 median: 0.9713313260898023 var: 151.64287135304312
    PASC mean: 2.0953481452049783 median: 0.9764705882352941 var: 77.07840207830598
    DTB mean: 1.0233705576544576 median: 0.9878937226078208 var: 0.06792388869939346
    RADS mean: 1.1364403402781202 median: 1.003184713375796 var: 0.643578806173884
    TRUE mean: 0.8493173268803796 median: 0.8632478632478633 var: 0.09021078212883271
    SLR mean: 1.0783466051254826 median: 1.0126078301260784 var: 0.22111516421142544
    THC mean: 1.408761115251278 median: 0.9756097560975611 var: 15.867601095526684
    MUE mean: 1.7363736446580782 median: 0.9888587359434626 var: 46.58774680996601
    PPY mean: 3.3287140543092595 median: 0.9927536231884057 var: 275.2170198997335
    CV mean: 1.0576339721129255 median: 0.8013517095149749 var: 0.8720319041174333
    LA mean: 3.3990212133887256 median: 1.0318833877477358 var: 136.435869796043
    OAX mean: 1.1299050771637256 median: 0.9669982783920874 var: 0.3609923463937279
    ALQO mean: 1.149181752030564 median: 0.9809523809523809 var: 0.45050493994893603
    XPM mean: 1.0629571821399466 median: 0.9769678215397872 var: 0.2655423411448323
    PARETO mean: 0.8910775237204194 median: 0.8374618425661812 var: 0.24245989680857696
    DAI mean: 2.077498826398061 median: 0.9901960784313726 var: 14.826653020588772
    EDR mean: 27.36711413003795 median: 0.9639501366375921 var: 74031.7168736374
    TGT mean: 1.093521801459007 median: 0.9689438372927127 var: 0.36305956949656304
    CAN mean: 23.070875064526717 median: 10.192789329605684 var: 3102.7464426388733
    COV mean: 1.3836502711268222 median: 0.8602941176470588 var: 1.5360817684235335
    ICOS mean: 2.2574171782592174 median: 0.9668847958392437 var: 39.235595710872374
    WCT mean: 1.1701535561908154 median: 0.9530903328050714 var: 1.101211677057518
    MOT mean: 0.9813440518945181 median: 0.8695721644825709 var: 0.2294584763288701
    PHR mean: 1.162301483754767 median: 0.9638554216867471 var: 0.3058186729078059
    REM mean: 0.008877812499999999 median: 0.008877812499999999 var: 0.0
    CAT mean: 3.816840392723796 median: 1.0453230472516875 var: 179.23927727792218
    BSD mean: 1.5371170948167738 median: 0.9774935007421865 var: 20.64193830796751
    DRT mean: 1.0389987448161093 median: 0.8928445185072967 var: 0.3741419836131954
    XSH mean: 1.656699802319672 median: 0.888968481375358 var: 4.012120871059148
    PRO mean: 1.6315287939472165 median: 1.0394724205269392 var: 10.419340277632534
    OK mean: 1.3703000747963716 median: 0.9978027343749999 var: 14.537045470135784
    LMC mean: 1.1322131518237863 median: 0.9763602497377256 var: 0.5979894784470184
    FLO mean: 1.1473930348763817 median: 0.9866390363708599 var: 1.288602122425286
    DNA mean: 1.263655752008851 median: 0.8578940300203509 var: 0.8834009905773688
    AUR mean: 3.3135468122674463 median: 0.9920735084485689 var: 1117.9582421538123
    NYC mean: 5.997012597952123 median: 0.9374999999999999 var: 2791.295804192803
    RBY mean: 1.0949218155500478 median: 1.024857324581709 var: 0.26590755983050723
    IPL mean: 0.8473129873960782 median: 0.898056484275191 var: 0.042163318253267766
    BOT mean: 1.227157050268349 median: 0.9270368171021378 var: 0.8725312879078536
    BBR mean: 1.099492434663026 median: 0.9315440681369828 var: 0.6379505802960121
    NEU mean: 1.0437694206490018 median: 0.8896103896103896 var: 0.35281722088435075
    BDG mean: 0.7833861010826637 median: 0.7880898777203902 var: 0.006858924107580044
    SWT mean: 1.2111273659149402 median: 0.9834254143646408 var: 1.1038870727524919
    ENRG mean: 1.1883565897540123 median: 1.002515258037867 var: 3.196645108407934
    RVT mean: 1.253850934159342 median: 0.9711546859330156 var: 1.0165094052546206
    EAC mean: 1.1247654401867053 median: 0.9494949494949495 var: 1.036596881080407
    INCNT mean: 2.1249915370082557 median: 0.988499573473192 var: 78.09110635653927
    AIR mean: 1.0289170720130913 median: 0.9879221034686251 var: 0.178265112667965
    OCT mean: 1.2345222435959708 median: 1.0389808638151206 var: 1.2453895216803716
    XMY mean: 1.138147842091564 median: 0.9777777777777777 var: 1.902587827555666
    UNIT mean: 1.4190888986042358 median: 0.986111111111111 var: 5.85004346613609
    DIVX mean: 1.1015015742256 median: 0.9351535836177475 var: 0.2070535922745646
    PST mean: 1.022010504453278 median: 0.9717493500054997 var: 0.13469346754505274
    HKN mean: 2.7947106686135506 median: 0.8448275862068965 var: 29.631260040753027
    TOA mean: 0.9980092476083768 median: 1.0077599586135542 var: 0.047241483771070215
    OTN mean: 15.679513684135518 median: 0.9792387543252595 var: 5141.324858808488
    HBT mean: 1.1240345171706492 median: 1.0573841063675387 var: 0.3180859629495144
    GOLOS mean: 1.0834835209175568 median: 0.9485870755750272 var: 0.3778635509640595
    RMC mean: 15734.462290813246 median: 1.3636363636363635 var: 844767215.4228815
    ALIS mean: 1.0194888286117567 median: 0.9288496552953709 var: 0.13831238133253057
    STX mean: 1.05631192840624 median: 0.9747899159663865 var: 0.21124697956957436
    BITUSD mean: 1.0418117620054925 median: 1.0096153846153846 var: 0.051016832875384915
    MUSIC mean: 1.0901632046297387 median: 0.975473309189412 var: 0.23877837769851828
    NXC mean: 1.1533720978853594 median: 1.0319146833241084 var: 0.6595181067748941
    GAM mean: 1.2018908204525003 median: 0.9906598171992796 var: 2.585433910862804
    SYNX mean: 1.3314578946900368 median: 1.009713599038654 var: 4.0224423120191055
    DBET mean: 0.9902465989854318 median: 0.9281480716609014 var: 0.14353133935624754
    PRG mean: 1.5200597212636144 median: 0.9149754006555916 var: 5.971079714193492
    PTOY mean: 1.0991203846228772 median: 0.9704277888135271 var: 0.2618967614281279
    SNOV mean: 1.5157960955196486 median: 0.8771762004974172 var: 2.9723412885309717
    CSNO mean: 1.1086204818326075 median: 0.9943709180804331 var: 0.2843887268990479
    DICE mean: 1.734483897816201 median: 0.9659863945578231 var: 11.864821242926281
    XSPEC mean: 2.338042701975048 median: 1.0109592095354452 var: 107.11217019163281
    CLAM mean: 1.0850884068235296 median: 0.9969788858825176 var: 0.47732296220573034
    XRL mean: 1.0999063475523916 median: 0.9964295492515463 var: 0.3269028120284622
    XUC mean: 1.5140333480749264 median: 0.9785407725321887 var: 4.62070057945712
    NEOS mean: 1.4160082803355931 median: 0.9561868944937251 var: 10.78281031904632
    FDX mean: 1.3836223600895328 median: 0.8043254702491895 var: 5.1734681393920345
    QAU mean: 1.0313546805631502 median: 0.9727967591966327 var: 0.07396724956366035
    BIS mean: 1.3721008937071668 median: 1.085739535031083 var: 1.0425829648640283
    NTRN mean: 1.8936589457787443 median: 1.0077770751200874 var: 126.07107933897592
    IXT mean: 1.1033475063273417 median: 0.9401476770507708 var: 0.2428526152660743
    TIE mean: 1.0541986406907213 median: 0.9622145712137401 var: 0.23376012603265903
    PZM mean: 1.0972818029753737 median: 1.0187830687830688 var: 0.36765567681606487
    ESP mean: 2.9751944563096444 median: 0.9606741573033708 var: 199.08151279802303
    DYN mean: 20.56096107038706 median: 1.0074130767258092 var: 25643.582824928566
    RNT mean: 0.8837890799885264 median: 0.96735236625899 var: 0.10607325536243828
    PRA mean: 1.268854536187598 median: 0.972446556173464 var: 1.0484328572576418
    XAUR mean: 13.322596062868785 median: 0.98844861383366 var: 24419.998121733614
    B2B mean: 1.766946826926218 median: 0.875979603709661 var: 10.130274722392462
    LUX mean: 1.2634930837530318 median: 0.9692307692307692 var: 0.646134333774713
    HAC mean: 0.9066259665769988 median: 0.9484578351497195 var: 0.20353912557568626
    GCR mean: 1.0709069282893664 median: 0.9772497636974022 var: 0.3235101505463763
    PND mean: 1.238368408359184 median: 1.0309278350515463 var: 0.8002330144712494
    FLDC mean: 1.4253147195606486 median: 0.9623287671232877 var: 15.640214400465254
    PLBT mean: 6.432785214436398 median: 0.9600614439324117 var: 1361.7959610777636
    HOT mean: 0.8638481986252674 median: 0.7610190631900082 var: 0.23736598372309192
    ATB mean: 1.657427238737646 median: 0.9265197823949393 var: 14.157342049122054
    EKO mean: 0.9821196155397733 median: 0.9083204843955747 var: 0.3023719090922547
    MYST mean: 1.7526218595724044 median: 0.9710082425834821 var: 27.480465265468066
    NVST mean: 1.071704820916102 median: 1.0133333333333332 var: 0.1734041589789394
    PUT mean: 1.2903953191424742 median: 0.9553283966516419 var: 3.239608575267986
    XLR mean: 1.4488974591883872 median: 1.0609552957304196 var: 5.129143327120182
    AXP mean: 0.7622983531873352 median: 0.8540011679025132 var: 0.11900365258571485
    DRP mean: 2.163532018089483 median: 0.9956069756187736 var: 27.191866208263942
    MDT mean: 0.7918302206348312 median: 0.811453358802929 var: 0.04394888424260693
    TX mean: 1.4054626546310303 median: 0.9961549251656193 var: 9.87011876749359
    IOP mean: 1.2384922448406095 median: 0.9787234042553191 var: 2.438240900790123
    LOC mean: 1.0545866910517394 median: 0.8905852417302799 var: 0.3394107279138523
    COFI mean: 0.7322008498879523 median: 0.8056415636701724 var: 0.06622575269728903
    TCC mean: 1.0411782769655527 median: 0.9357811750768623 var: 0.1498463903023201
    COVAL mean: 1.1021534118386882 median: 0.9837398373983739 var: 0.43954840885192364
    WRC mean: 1.6252876169909811 median: 1.0075979771812547 var: 4.546096546992434
    ECN mean: 1.7351393968520081 median: 1.0263157894736843 var: 20.20062134500797
    LEV mean: 0.7677054207697698 median: 0.8528018076479567 var: 0.11506091026094237
    GET mean: 6.891596424600101 median: 0.8380462724935732 var: 322.38051199561886
    BQ mean: 1.0136743054823159 median: 0.9119683481701287 var: 0.23590175782961267
    CURE mean: 1.6097701137009595 median: 0.975659560565221 var: 82.569954261555
    REBL mean: 0.8654994838528253 median: 0.9406158427296607 var: 0.09303078295401579
    DBIX mean: 1.3158345488980958 median: 0.9488559892328399 var: 3.5487143910212495
    POLIS mean: 1.6330185683122835 median: 0.95392077607114 var: 4.851214281611902
    CXO mean: 0.7857543701354938 median: 0.8094809292015893 var: 0.2053173947266654
    HORSE mean: 1.0672140845640967 median: 1.0147014760920423 var: 0.10520179352275152
    BLUE mean: 1.2507070615819034 median: 0.9692334183763118 var: 0.4372427274603526
    CREDO mean: 1.0569311130422596 median: 0.8851647539772447 var: 0.3120750999462818
    BCY mean: 1.050471226306748 median: 0.9954002216760637 var: 0.07960842503409356
    PINK mean: 1.2571045297030272 median: 0.9825174825174825 var: 4.237625162129359
    BNTY mean: 1.5501313097681713 median: 0.93709136093664 var: 3.2176429892609106
    PFR mean: 1.2396951697205065 median: 1.0680368263449207 var: 0.5471245973900587
    SPF mean: 1.1271001518553714 median: 0.9224157947023649 var: 0.3312425674590844
    SPHR mean: 2.1189085774543566 median: 1.0159235668789808 var: 109.98608488642697
    MEE mean: 0.748997656770588 median: 0.7910586055130878 var: 0.11317717677015884
    NIO mean: 1.2749009288566853 median: 0.9335333607680072 var: 0.9480108468858326
    AVT mean: 1.6672911296727069 median: 0.92578125 var: 13.915359460093145
    SXUT mean: 0.9188911268006769 median: 0.9311304501479877 var: 0.08594179165795199
    OBITS mean: 1.2598757203363713 median: 0.9815379825653799 var: 5.284962892836087
    NVC mean: 1.059451005101136 median: 0.9784690499834492 var: 0.2723685948646275
    ATMS mean: 1.0462416032966924 median: 1.026803277699335 var: 0.08631803748666297
    XST mean: 1.3764431779470718 median: 0.9837872749568028 var: 13.977923277661127
    FLIXX mean: 1.0616849298481534 median: 0.964918406245886 var: 0.303457695105963
    USNBT mean: 1.032911768689117 median: 0.99768985677112 var: 0.15239284395207325
    EBTC mean: 1.1301481134562879 median: 0.9845775279604315 var: 0.45729449538530625
    GBX mean: 1.9618383434127789 median: 0.9679037111334001 var: 16.459371388331043
    KORE mean: 1.5674950296426946 median: 0.9964427704540698 var: 51.219197880163755
    BIO mean: 0.3241242879226531 median: 0.0055746621621621615 var: 0.24378073876749157
    KRM mean: 1.2137715505334452 median: 0.8888919537693432 var: 1.3371275941472827
    BTCZ mean: 1.0996180137363618 median: 0.9385796545105565 var: 0.26582951119561044
    LINDA mean: 1.1127069730849761 median: 0.9294478527607363 var: 0.26582851283353975
    SEQ mean: 1.3448560422124824 median: 1.0263968143191429 var: 3.1734285271970086
    PIRL mean: 1.1093456405163835 median: 0.9396551724137933 var: 0.1348284380796401
    MYB mean: 1.1462418390847575 median: 0.9828973843058351 var: 0.5203888388257866
    ELIX mean: 1.2131474829342375 median: 0.9627679337868831 var: 1.193649661705744
    PKT mean: 1.2273871953414424 median: 0.889795918367347 var: 0.606223309491471
    HEAT mean: 1.2045059544738905 median: 0.9880750262753658 var: 1.9628736292328597
    CVCOIN mean: 1.090182010648841 median: 0.9946934012487116 var: 0.22462714837129305
    CHIPS mean: 1.0782710779078373 median: 0.9347758395664529 var: 0.33892351037467233
    ASTRO mean: 1.3158533650207291 median: 0.9846827133479211 var: 2.3115714981005118
    ABY mean: 1.495282182629039 median: 1.0103092783505154 var: 37.49898657810858
    LOCI mean: 15.779436933349801 median: 26.933038141847277 var: 163.786478932277
    HGT mean: 1.1398872814825693 median: 0.864458722008656 var: 0.6855457633468249
    AID mean: 2.5662973355293643 median: 0.8758859333433223 var: 18.858296452219832
    DOPE mean: 1.7826750755579917 median: 0.9854545454545452 var: 58.738625489954295
    OXY mean: 1.0927925202043904 median: 0.8946753726478641 var: 0.20259034446327173
    VOISE mean: 1.075212513145814 median: 0.943535703051274 var: 0.2950758545560318
    DOVU mean: 1.2709157310049675 median: 0.9741664274763984 var: 1.2161280809372386
    FRD mean: 1.237008108505727 median: 0.8696552178297356 var: 2.3279005257814123
    CAG mean: 1.222984686008029 median: 1.0277975086704316 var: 0.8726049135126474
    AIT mean: 0.8624283113281533 median: 0.8950943098205941 var: 0.026765348482615896
    XVC mean: 1.1374593923426657 median: 1.0020544111986662 var: 0.6029559391173379
    ARY mean: 0.8800168462133474 median: 0.9188336071344754 var: 0.11377640211397791
    EVE mean: 1.1581165403920353 median: 0.9855981482968188 var: 0.34987280170290636
    APX mean: 1.4115807340909652 median: 1.0203619909502262 var: 7.700033391624072
    HYP mean: 1.5541757142291013 median: 0.9723691945914166 var: 42.26489637058621
    PLAY mean: 1.850000662046165 median: 0.9151673600451284 var: 7.49363384511216
    QWARK mean: 1.0498675173697838 median: 0.9737637831078776 var: 0.12883979721159933
    RMT mean: 1.5246535194398676 median: 0.6273426930157251 var: 5.1954153367980895
    BRX mean: 1.289726932175237 median: 1.0125786163522013 var: 4.445821806851341
    DNR mean: 1.1753179036139567 median: 0.9410084359204665 var: 0.785054314021061
    GAT mean: 0.8155515396250428 median: 0.8314961394648669 var: 0.1264849136364992
    TIPS mean: 1.2848348363326754 median: 0.9058823529411765 var: 3.6901786256601676
    STAR mean: 159.7011099226092 median: 0.8860479882667525 var: 342340.3409922586
    VTR mean: 1.116587810790536 median: 1.0093343940534345 var: 0.3344888750672981
    POLL mean: 1.1127356796372587 median: 0.929368029739777 var: 0.19327418314953426
    MEME mean: 1.4427840066166238 median: 0.9827586206896551 var: 16.031393084622703
    PIX mean: 1.1450195827697074 median: 0.9219788861616186 var: 1.252867449446521
    BEZ mean: 4.201007725898556 median: 4.201007725898556 var: 0.0
    SNRG mean: 1.207260408423617 median: 0.9984372746069146 var: 1.4747087740973845
    PTC mean: 2.1284388118588993 median: 0.9897435897435898 var: 403.8428247198915
    ERC mean: 1.3594177291619467 median: 0.9983351831298556 var: 7.26144236126295
    TRF mean: 0.6958907761304691 median: 0.8364449438543479 var: 0.19123318280167573
    BPL mean: 1.0696929639591566 median: 0.9842919785475674 var: 0.10097204243429232
    ZLA mean: 0.9956366494692054 median: 0.9687174199461532 var: 0.038240113491832976
    VZT mean: 1.3957714586546341 median: 0.8243617010976387 var: 3.24443468695921
    BET mean: 3.4996885175832197 median: 0.9817073170731708 var: 129.60354550312059
    VRM mean: 2.431036926236248 median: 0.9572953736654803 var: 65.1763717167199
    VIU mean: 1.1848077523483864 median: 0.9212256042066942 var: 0.6687132438113924
    KLC mean: 1.3423529431026744 median: 0.995100707675558 var: 2.170787255414133
    AIX mean: 4.570919136333871 median: 1.0042189096618293 var: 131.89320816189593
    DOT mean: 1.2329591628214416 median: 0.9994582881906825 var: 5.002505658244162
    GLD mean: 1.1134066230173767 median: 0.9702563777129077 var: 0.6174478891091038
    SUMO mean: 1.1778834159117866 median: 0.97078186496581 var: 0.697962826634442
    FLIK mean: 1.0112227387355905 median: 1.021908550874707 var: 0.14000720347604062
    UFO mean: 3.2949526313077575 median: 0.9545454545454545 var: 41.94002431208869
    XBC mean: 15.576158542327516 median: 0.9643400773354011 var: 53940.6067746482
    TFL mean: 1.0989545383387784 median: 0.9125150041706508 var: 0.560535657360255
    ERO mean: 0.8735775269057959 median: 0.9482155664927163 var: 0.03939536455237032
    CPAY mean: 1.466153096369868 median: 0.897058145514514 var: 3.6465151728705134
    EVC mean: 1.1280640101584878 median: 1.0967104873975582 var: 0.19942312397875817
    1337 mean: 1.294254609127999 median: 0.9605901766647253 var: 3.029293447868572
    TBX mean: 604.6392466340978 median: 0.8978134615384615 var: 2551453.5333813564
    EXCL mean: 3.044511584204507 median: 0.9839704069050556 var: 491.85517829548553
    CRB mean: 1.0931518358140468 median: 1.0039969849333306 var: 0.22046766076358912
    HUSH mean: 2.502148614324613 median: 1.0335195530726258 var: 79.50788564742417
    ADB mean: 0.7691533064703481 median: 0.9077710237460097 var: 0.1284196742751535
    ZRC mean: 70.21226543487823 median: 0.9948453608247423 var: 244752.86249376804
    2GIVE mean: 1.1758937469103896 median: 1.0099246462047418 var: 1.7349672091955128
    ING mean: 5.201447007586925 median: 0.9925362705490766 var: 79.59691092961057
    BRK mean: 23.832907241806343 median: 1.0095172643591985 var: 63293.95458999206
    GMT mean: 1.001057993423181 median: 0.8571566450035961 var: 0.24004551134670737
    PBL mean: 1.32807997576479 median: 0.9923023950597254 var: 1.1412129428462023
    MCAP mean: 1.302684091505846 median: 0.9532374100719425 var: 4.881755761027494
    MONK mean: 1.7763810844968735 median: 1.0047844746160068 var: 6.678376969190059
    SSS mean: 0.9782368516655066 median: 0.8970446428918466 var: 0.19435435751531055
    SCL mean: 5.928412215985811 median: 0.9681739089142226 var: 751.2476425019565
    TKS mean: 1.0593227398079341 median: 1.0113636363636362 var: 0.07532681384288166
    WISH mean: 1.036897743002585 median: 0.9916846085900409 var: 0.21819008961059652
    BELA mean: 1.4017856766749774 median: 0.9886363636363636 var: 10.542322465199469
    BLITZ mean: 1.4681209290129003 median: 0.9861413091513319 var: 19.65837969999813
    BON mean: 1.060026109397508 median: 0.9370078740157479 var: 0.2428803578566621
    GJC mean: 1.2982918451789027 median: 0.7594796588886144 var: 0.7598457525517163
    PBT mean: 118.17808409132735 median: 0.9658052959225298 var: 584551.4396904241
    INXT mean: 1.0936859863678805 median: 1.0508474576271187 var: 0.21862189163202522
    RC mean: 1.2745034450504265 median: 1.0071330589849108 var: 1.9236898921025385
    BUN mean: 2.134230484684848 median: 0.9896907216494846 var: 97.87027702056568
    STA mean: 207.77070972850552 median: 1.000926693654587 var: 1923389.1903850464
    CRED mean: 1.0686276683848241 median: 0.8952490566037735 var: 0.360354395249506
    REAL mean: 1.189012078433081 median: 0.9695255921964697 var: 0.7365051225464836
    RIC mean: 1.1154851304636912 median: 0.9717370823972752 var: 2.568368665074745
    NSR mean: 1.114798237424875 median: 0.9878765613519471 var: 0.6417125994016526
    CANN mean: 1.225950205198043 median: 0.9860912981455062 var: 3.4605329872625243
    HUC mean: 1.1810919948871788 median: 0.9654146522870957 var: 5.216621413686453
    PDC mean: 1.1491918592454193 median: 0.9851111347442306 var: 1.441609131657334
    BWK mean: 4.408091073497695 median: 0.8434684684684685 var: 184.36971669701586
    TRUST mean: 1.4009098214916818 median: 0.9914495114006515 var: 15.975226734337134
    ALT mean: 1.3376578006406636 median: 1.0533333333333335 var: 3.036369314323164
    BTDX mean: 1.5723247458844238 median: 0.9929577464788732 var: 18.057960432692063
    TES mean: 1.3420304552523574 median: 0.9902597402597402 var: 20.440813064127905
    SENSE mean: 0.9604919678492622 median: 0.8453721293913765 var: 0.08044280502673554
    SPRTS mean: 2.589886376424473 median: 0.9666666666666667 var: 168.22361151723635
    GCN mean: 1.3077650716847427 median: 0.9629629629629629 var: 2.5507282898270156
    VSL mean: 22.342980784133864 median: 0.9823904591694125 var: 38146.42091243587
    TZC mean: 1.1012806861205726 median: 1.0049217788715064 var: 0.29838681343109374
    MNTP mean: 34.2301231974635 median: 0.886039886039886 var: 4033.893423611197
    TRCT mean: 0.9637948853478386 median: 0.881667397559818 var: 0.10720853779459141
    QRK mean: 1.3663221041901343 median: 0.9667641509271346 var: 8.442894401325463
    KRB mean: 1.1771070211130152 median: 1.006079429062314 var: 1.0550629176387551
    MTNC mean: 1.0130051565926916 median: 0.9721852403995632 var: 0.10308532358258911
    SLT mean: 3.337404479327089 median: 0.7034220532319392 var: 40.36457121985603
    FYP mean: 1.0775481873158415 median: 0.9431531267038543 var: 0.2341569143749868
    XMCC mean: 1.1559211970315124 median: 0.9459087681666953 var: 0.3054946043709651
    WILD mean: 1.0691959634485757 median: 0.9729273497467912 var: 0.27053290797546903
    ADST mean: 1.0489513810725704 median: 1.048823011873468 var: 0.08492124796629574
    BTW mean: 0.9080178983976493 median: 0.898151421338104 var: 0.06712511723196732
    SWIFT mean: 1.1557846897611936 median: 0.9895510493225892 var: 2.810416156844824
    DGPT mean: 1.1268738693009772 median: 0.9645390070921988 var: 0.19215332280439187
    UFR mean: 1.164061727780529 median: 0.9493052355893978 var: 0.5744256812792038
    ADC mean: 1.1201657079268712 median: 0.9938971786433205 var: 0.41225953778811014
    OPT mean: 1.2654087071118445 median: 0.9864032022364827 var: 1.9601185949718776
    VSX mean: 1.1336646849318335 median: 1.0170636331318876 var: 0.3988681638899477
    HAT mean: 1.895724391296752 median: 1.073321554770318 var: 8.536811195952382
    LIFE mean: 1.1332912913463637 median: 0.9911111111111112 var: 0.5394233284886975
    EGC mean: 1.4340980808114878 median: 0.9910417338859795 var: 5.136328442144236
    SEND mean: 1.1395337435305881 median: 0.7576546721917834 var: 0.8375857569366276
    MZC mean: 2.1546794877748128 median: 0.9823529411764707 var: 312.85506445780106
    IXC mean: 1.2195350341010938 median: 1.0005479881008297 var: 2.7031104459695623
    DFT mean: 1.1961078423700704 median: 1.215559298408642 var: 0.08063861304863568
    ZEIT mean: 1.1688016836535604 median: 0.9743589743589745 var: 1.1641488456512497
    SPR mean: 1.323393255949546 median: 0.9900138965194065 var: 6.337818927064483
    ZER mean: 1.1443930699673923 median: 0.9439049225042524 var: 0.61448524661519
    NOTE mean: 1.110389484001424 median: 0.9847335059369698 var: 0.7831027078484148
    CREA mean: 1.1183685492270197 median: 1.0275503377430562 var: 0.32393558599951716
    ATL mean: 1.1230246701033268 median: 0.9644375870244232 var: 0.4609881474503184
    ODN mean: 1.0583347474500053 median: 0.9056533294142142 var: 0.2863008743153113
    CHC mean: 57.83032796985446 median: 0.9914751914751916 var: 462886.80469233164
    SXC mean: 1.1353849882848164 median: 0.9757516973811833 var: 1.977944046713404
    EFYT mean: 3.9017534531536717 median: 0.9728703201302225 var: 402.85179890113625
    BUZZ mean: 1.0374226685143586 median: 0.927289896128423 var: 0.2243049766546217
    TRC mean: 7.042171026202808 median: 0.9687038677295543 var: 11135.869022013829
    BLU mean: 3.045896235074903 median: 0.9487179487179487 var: 767.5465696348574
    EFL mean: 1.0917182067084763 median: 1.0029030817329163 var: 0.366985543642976
    ELLA mean: 1.136883538683611 median: 0.8933426256883013 var: 0.32801892302495317
    HWC mean: 2.885699836941764 median: 0.9305869074492099 var: 55.99533793149023
    YOC mean: 1.3014039046315762 median: 0.9241068771943746 var: 5.574995543835277
    START mean: 1.2028488357869656 median: 0.9602082558571959 var: 4.091023872946697
    IND mean: 1.0342602481835659 median: 0.9575520120448945 var: 0.09141111107839836
    PKB mean: 2.010799601049847 median: 0.9908105883966534 var: 85.38381646763277
    CARBON mean: 1.3270512316043501 median: 1.0416666666666667 var: 3.970129693142396
    QVT mean: 39.40107303635356 median: 1.0413968434355803 var: 33997.93880845199
    SAGA mean: 1.3058387582869537 median: 0.9227272727272726 var: 1.397571191746391
    XMG mean: 1.126377029402008 median: 0.9770841974284529 var: 1.6934549203930513
    CL mean: 0.8502251190337755 median: 0.8133462162597398 var: 0.03412391221252627
    ETBS mean: 10.734256142650949 median: 0.9515418502202644 var: 3433.7876737961174
    MXT mean: 4.193436584103087 median: 0.9913479052823315 var: 1075.2211228952435
    WTT mean: 1.0651463696783197 median: 0.9157303370786516 var: 0.3249425761163913
    ZNY mean: 15.584616331700472 median: 1.0078125 var: 38960.725715272776
    MRJA mean: 2.9137665880444885 median: 0.1623931623931624 var: 1235.1660313289792
    RUP mean: 1.2369079627522581 median: 1.001426315764367 var: 1.3056917600702094
    JC mean: 0.4250907672867078 median: 0.5525727069351232 var: 0.06828961125296226
    GOOD mean: 1.5411943650502926 median: 0.951338199513382 var: 7.668360993792567
    HXX mean: 0.9769468178581774 median: 0.28624535315985133 var: 13.622429478687433
    SMS mean: 8.95586194292203 median: 0.8747970120168885 var: 366.80975128654495
    STAK mean: 1.1659363914722736 median: 0.768361581920904 var: 2.325941426634135
    INN mean: 1.076865386444757 median: 0.9708561020036429 var: 0.15817878527283874
    AMM mean: 0.9505508876383159 median: 0.8897299828312785 var: 0.14674904974920827
    BDL mean: 1.0592024070559665 median: 0.9304781324381112 var: 0.4776707524758908
    ZEPH mean: 1.0781819165905406 median: 0.9840400777464483 var: 0.15773677423687363
    LINX mean: 1.0865888742065248 median: 0.9784314380154251 var: 0.1415408234037493
    STU mean: 1.0256312242379126 median: 0.971017341215246 var: 0.09958944444309431
    ITNS mean: 1.1381908769220006 median: 0.9107736676618028 var: 0.5705444976763465
    REC mean: 37.54437108620889 median: 0.8734780307040763 var: 40058.36325968582
    MAGE mean: 11.942197270436628 median: 0.8317152103559871 var: 470.074465690933
    FYN mean: 1.1771400413509108 median: 1.0060975609756098 var: 0.922246955563071
    HOLD mean: 0.9728434146606488 median: 0.7896678966789668 var: 0.4592908474329887
    PROC mean: 1.3020216738019792 median: 0.9249731238565851 var: 1.7743156821491421
    NKA mean: 1.3842338381253425 median: 1.0104166666666667 var: 4.95230425000401
    MAG mean: 65.6817838275649 median: 1.3694231228465188 var: 74849.75627250802
    OCL mean: 1.0890171319331663 median: 0.9805330123351322 var: 0.44214676163951716
    CMPCO mean: 1.44400537279289 median: 0.8791469194312798 var: 2.437787811647702
    LCT mean: 402.41381604325943 median: 0.7089947089947091 var: 1385532.2150136621
    FOR mean: 1.6135218416101638 median: 0.9338754374254101 var: 4.612404253708197
    XGOX mean: 1.0319297854039462 median: 0.8612256923983501 var: 0.28850448616667246
    IFLT mean: 1.1395257362528421 median: 1.0540540540540542 var: 0.4303369451610134
    ONG mean: 93.51602853173588 median: 0.9090272130121989 var: 146532.62649993884
    GRE mean: 1.171588969650202 median: 0.9606299212598425 var: 0.8354541737251248
    UNB mean: 3.9750490288118128 median: 0.9711993151429505 var: 2013.3185078887802
    UNY mean: 1.4380205711109215 median: 0.9283970034352881 var: 10.450403752262766
    PYLNT mean: 109.07466444257415 median: 0.9579439252336448 var: 135639.7048764647
    EMV mean: 1.3525574981535111 median: 0.9883459793628802 var: 1.857876333832413
    VIVO mean: 1.0702045996953091 median: 0.9351351351351351 var: 0.19026498849016518
    RAIN mean: 1.2991828617203514 median: 0.9571144809665246 var: 4.650100605337457
    ANC mean: 1.136080118468218 median: 0.9768409436607114 var: 0.7270964741837301
    EBST mean: 1.0650324715279618 median: 0.9842378814128626 var: 0.2263493716400684
    ADZ mean: 1.0620448932197197 median: 0.9636433176710111 var: 0.28166236265227507
    DAY mean: 5.802183137241963 median: 0.983402489626556 var: 706.9291534187796
    MRT mean: 1.0271206217960553 median: 0.9836236933797908 var: 0.10030072767537666
    MBRS mean: 1.2458305076134293 median: 0.9455216682741877 var: 0.9633392238306873
    OPC mean: 0.9215820631957398 median: 0.804702122803013 var: 0.12377572511471141
    IC mean: 251.27872908808845 median: 0.878099173553719 var: 501579.45597081044
    DP mean: 2.313917606939172 median: 0.9855072463768116 var: 194.0583933776179
    EQT mean: 1.123493680568476 median: 0.9744827558093795 var: 0.4598928839274097
    PURE mean: 1.15853149268877 median: 0.9067796610169493 var: 0.3848087188129947
    PLC mean: 0.9774420791356034 median: 0.9420289855072466 var: 0.6474993866774404
    PHO mean: 1.3445503256949918 median: 1.049099967855995 var: 3.704341336402258
    

    c:\users\generic\appdata\local\programs\python\python36-32\lib\site-packages\numpy\lib\function_base.py:4033: RuntimeWarning: Invalid value encountered in median
      r = func(a, **kwargs)
    

    42 mean: nan median: nan var: nan
    SMLY mean: 1.2473960526566241 median: 0.8888888888888888 var: 3.159026175122162
    SKIN mean: 8.34804435329769 median: 0.9558557600255292 var: 2366.019989018574
    AI mean: 39.02328107732242 median: 0.8713646532438479 var: 26766.70648854292
    BYC mean: 1.110764546469191 median: 0.979555167548143 var: 1.1197233899042134
    ACC mean: 11.09551253697273 median: 0.9047396902407167 var: 573.8345589673693
    UNIFY mean: 1.0983995462369094 median: 0.9565774060857011 var: 0.2790235710394744
    GCC mean: 6.280578217595042 median: 0.8898305084745763 var: 1334.7444550256873
    ORB mean: 1.2353587198440872 median: 0.9935241278462503 var: 16.08941919894776
    PING mean: 1.061540455441808 median: 0.9428713786245693 var: 0.3180322013286436
    GRWI mean: 1.1006863290432707 median: 0.9628808103015075 var: 0.1670326505331953
    LDOGE mean: 1.4907718945290822 median: 0.9347826086956522 var: 21.2172915052311
    NOBL mean: 1.0968075632644871 median: 0.96 var: 0.5163724622372392
    CNT mean: 2.145908810861626 median: 0.9515701853953841 var: 64.2403352360764
    BTCA mean: 0.8938905459521225 median: 0.8686825667234526 var: 0.04689626570324015
    ELTCOIN mean: 1.1997364106139996 median: 1.1336856527696222 var: 0.33212787192237503
    KEK mean: 1.0777632075895136 median: 1.0254457271671562 var: 0.1030489955281911
    BRO mean: 1.0721746425733756 median: 0.9516170164535201 var: 0.20555829642800558
    CRM mean: 1.047357217393601 median: 1.0048824307328585 var: 0.14933332046647407
    XFT mean: 6.624740337920457 median: 0.7704081632653063 var: 4296.105345215604
    EPY mean: 1.007975794185807 median: 0.9401603020660089 var: 0.24476171562547916
    CDN mean: 1.31065593202916 median: 1.002902757619739 var: 8.628083246277592
    STRC mean: 1.545979475544048 median: 1.0064707464957228 var: 9.165736826336051
    ICOO mean: 1.1686786560230629 median: 1.0176470588235296 var: 1.4328870565728595
    CRC mean: 1.0311067136110412 median: 0.8554089709762533 var: 0.15893864033632382
    MOIN mean: 1.1705556958965702 median: 1.0060062590274435 var: 0.802370013817592
    ZENI mean: 0.9981799555249317 median: 0.9660925726587729 var: 0.05485201424823093
    FST mean: 1.3286594420605349 median: 0.9702093397745573 var: 7.382922057061675
    Q2C mean: 2.2217300181888033 median: 1.374217772215269 var: 3.9832374763171723
    UIS mean: 1.2535486880241058 median: 0.9719492110715614 var: 5.5880959606077845
    ARC mean: 1.3314183610219779 median: 0.9397508779112798 var: 4.949165655240427
    BTA mean: 1.331672115896239 median: 0.9960212201591513 var: 4.593318035064948
    CDX mean: 1.0621421851243082 median: 0.9036755860555857 var: 0.49938926288441504
    INSN mean: 1.0785413677742939 median: 0.9475713485560954 var: 0.17649947196809707
    FJC mean: 1.2281557497285736 median: 0.9523809523809526 var: 2.7500819128100464
    XPD mean: 1.1639768460104967 median: 0.98005698005698 var: 1.19591167945884
    LGD mean: 2.626004115255399 median: 0.9226190476190477 var: 128.82498978781203
    BBP mean: 1.0590071044749785 median: 0.9713322091062395 var: 0.18313477232192013
    DCY mean: 1.0568119931446045 median: 0.9866369710467705 var: 0.18621850200756188
    KLN mean: 35.16770386590181 median: 1.0256410256410258 var: 35206.58856615931
    EQL mean: 0.7719082635126546 median: 0.8807279105459329 var: 0.15745367926366033
    ZET mean: 1.1314380886688755 median: 0.9796884243738908 var: 1.0898053201275661
    WDC mean: 1.1068251349934128 median: 0.973062043272675 var: 0.4590755327042462
    BTCS mean: 1.3202334039772599 median: 1.0103734439834025 var: 3.4956872914928887
    MAC mean: 11.725240011973723 median: 1.142857142857143 var: 335.63091254870614
    ERA mean: 1.367496050631179 median: 1.0240687679083096 var: 1.6147719375619731
    ARCT mean: 1.8358476365895962 median: 0.9584984470386635 var: 6.216853842034123
    KBR mean: 1.4214889054063649 median: 0.9028906002742905 var: 2.9477852540799767
    FUCK mean: 1.295846823721769 median: 0.9740129097158184 var: 1.324381288680783
    ABJ mean: 3.186330815894991 median: 1.0406330265843164 var: 50.24666394153927
    PIGGY mean: 9.70115352191001 median: 0.9748119960134094 var: 19404.739514200603
    XLC mean: 2.640080742309917 median: 0.9444805367922512 var: 109.5505466768636
    XPTX mean: 1.1067597149156847 median: 0.9664894659763142 var: 0.31455471574658117
    SKC mean: 3.8359583559099515 median: 0.9812206572769953 var: 2014.3360984805229
    TIG mean: 1.2176931824729023 median: 0.9687063541450599 var: 0.1365814844993677
    TROLL mean: 1.2138536967471905 median: 0.9615384615384616 var: 1.6642410670992789
    SCT mean: 7.061664394998316 median: 0.9855929157852202 var: 431.506520496333
    GUN mean: 1.372490920324566 median: 0.9769510715729883 var: 13.770367920836582
    RLT mean: 2.4710774500409975 median: 0.954239828662292 var: 116.81232956034003
    MAX mean: 1.1603397855668305 median: 0.9572649572649572 var: 2.6027231016439574
    ECASH mean: 1.9419885644196613 median: 1.0392557656382202 var: 21.77463851084337
    XCPO mean: 1.1327378576273115 median: 0.9125834837829989 var: 0.3820008895746833
    SUR mean: 4.191406584555131 median: 1.0314009661835748 var: 364.40461251434243
    BXT mean: 3.211295436288058 median: 1.0468904059421746 var: 308.1175525982697
    BTB mean: 1.5568368164670432 median: 0.9673541793819381 var: 28.681762442947008
    DEM mean: 1.0690759366699283 median: 0.9786662187132538 var: 0.38450761473504746
    DGC mean: 1.0963050162348895 median: 0.9755500336149963 var: 0.5500893120819472
    DEUS mean: 1.0836936867987288 median: 0.977760608922082 var: 0.33791643384287595
    POP mean: 1.66718918762942 median: 0.89 var: 29.918820015248418
    CCRB mean: 100.97954451774766 median: 0.9488942977802742 var: 782495.4014219709
    ARI mean: 1.9195397175661724 median: 0.9730094466936572 var: 152.5213820152938
    BRIT mean: 1.3430720960151215 median: 1.058980213089802 var: 1.7193098515439842
    JET mean: 1.2469009192992566 median: 0.9396152714236028 var: 1.1291835484189692
    SGR mean: 1.7482371661033882 median: 0.9213737348168131 var: 12.303498296349634
    EL mean: 1.2210689336293505 median: 0.960142647367317 var: 1.5848954738272445
    KOBO mean: 1.2595965167444114 median: 1.0190721649484538 var: 1.9992634042027189
    RUPX mean: 4.123991808885276 median: 0.813572979385366 var: 60.27013571342539
    ACE mean: 5.762210910664294 median: 0.9325146392691127 var: 270.2671097343926
    CYP mean: 1.1621232783777526 median: 0.993099121706399 var: 1.882974110631939
    FRST mean: 1.1852347540381412 median: 1.0266614716590838 var: 1.2473099880131042
    TTC mean: 1.2183257121214042 median: 0.9797297297297298 var: 1.1430000982104243
    BTWTY mean: nan median: nan var: nan
    HERO mean: nan median: nan var: nan
    DFS mean: 1.6982240373207087 median: 0.9321535714719493 var: 15.862879684759038
    CFT mean: 1.2083540330360405 median: 0.9340316566567595 var: 1.8633560449369537
    WAND mean: 3.233866830123268 median: 0.8166025620649098 var: 62.73426796792834
    ITI mean: 2.286264690035159 median: 1.0004391743522179 var: 74.61976582273371
    ERC20 mean: 2.018382103606003 median: 1.09478672985782 var: 13.017739113369965
    CTX mean: 4.499125123447405 median: 0.9121323482661714 var: 275.5624422429602
    HPC mean: 1.8061143679140494 median: 0.9993036009633519 var: 31.58787516492399
    CJ mean: 1.194889850930771 median: 0.963768115942029 var: 0.9759018629541839
    ATS mean: 1.4689577851662643 median: 0.9704455227172474 var: 4.308014537355025
    MEC mean: 1.109673685324911 median: 0.9745820539065164 var: 0.7747659806981313
    LANA mean: 1.4980608257602617 median: 0.9335548172757475 var: 13.277700997008655
    RKC mean: 16.658674621004565 median: 0.8627450980392156 var: 6492.978069238101
    TRUMP mean: 1.580517409382678 median: 0.9907982744290974 var: 15.159253056975963
    GAIA mean: 1.1662866485876902 median: 0.9954853273137699 var: 1.744219513911491
    TIT mean: 1.1852855788993573 median: 0.9756067667096818 var: 1.2381100947768804
    MNE mean: 1.7202068436017062 median: 0.9172173981486428 var: 17.394492154900792
    MANNA mean: 1.1661965257853661 median: 0.9961612284069099 var: 0.9037597392286816
    AERM mean: 4.257771391960339 median: 0.8522610483042138 var: 207.32607280753223
    UTC mean: 1.5059998595713022 median: 0.9664634146341463 var: 42.00659595446521
    XPY mean: 3.4670740004378864 median: 0.9757255936675461 var: 1256.5382484384156
    GLS mean: 1.7986914378631949 median: 0.8852754901325032 var: 14.957534822730741
    WHL mean: 1.1091364355586935 median: 0.9191004375699603 var: 0.6031637529345028
    ENT mean: 2.29353818226085 median: 0.8872294802321039 var: 111.71206224766534
    KURT mean: 1.2182602352287328 median: 0.9945701357466064 var: 0.9157389101574227
    SRC mean: 1.147578337613432 median: 0.9854596981019952 var: 1.2746075891365163
    RBT mean: 1.4747837711865874 median: 0.9782608695652174 var: 9.523235907031273
    MCRN mean: 1.3254343945851392 median: 1.0561797752808988 var: 1.8060289019113003
    MOJO mean: 1.2781190491690964 median: 0.9684093848143358 var: 3.525917258553119
    EBCH mean: 1.2364170140846995 median: 0.9730080296479309 var: 0.8201392516065784
    ETG mean: 1.149442084983062 median: 0.969484342706289 var: 0.5107067346737318
    OTX mean: 1.1249427433267483 median: 1.0247369951521865 var: 0.4433196587953288
    NETKO mean: 1.075295085717736 median: 1.0300748469040597 var: 0.16798481233013457
    VIDZ mean: 1.101837505314748 median: 0.9603914259086673 var: 0.3796070467853002
    BTCRED mean: 1.482006764974909 median: 0.8770446511194403 var: 2.3822745179562133
    PAK mean: 1.2424715471795893 median: 0.9640397857689366 var: 1.271221731888428
    STN mean: 18.313145052282422 median: 0.9109949537065285 var: 2862.921276891474
    IETH mean: 1.5976948461959777 median: 0.8781718628692846 var: 8.731832002572032
    SAC mean: 1.3958156590683775 median: 0.9689349112426037 var: 5.676883652689632
    SLG mean: 1.132421427867057 median: 1.0122558813561895 var: 0.7706888887258849
    AIB mean: 1.1997356462263455 median: 0.9764412239553215 var: 0.727480928395202
    XBL mean: 1.619134240876802 median: 0.929036094513462 var: 8.59901415722886
    PCOIN mean: 1.1396097082262953 median: 0.9200995261678018 var: 0.4294469662891106
    ARCO mean: 1.3059388818890136 median: 1.0119695321001088 var: 3.813490772069189
    XCN mean: 1.1654595308998992 median: 0.9413714553545738 var: 1.6141211058757312
    XHI mean: 1.3452877741618499 median: 0.9410377358490566 var: 10.206286706957764
    DAXX mean: 1.59250356419837 median: 0.9485682732507691 var: 16.37535892932204
    GRLC mean: 430.2584452856225 median: 0.569792596524916 var: 1143585.4164829066
    LCP mean: 0.9861114086956476 median: 0.891713747645951 var: 0.8050800665797375
    TAG mean: 1.1036970360389298 median: 0.9722010788628916 var: 0.9855864542825928
    8BIT mean: 1.2426110848455192 median: 0.9697264733623393 var: 2.068194893875782
    BITBTC mean: 4.047217342509546 median: 1.0084101785775244 var: 2181.6205039178753
    CUBE mean: 2.4263118218862676 median: 0.9473684210526315 var: 642.057116850981
    GB mean: 1.2071094908294007 median: 0.9674239177025289 var: 2.010431707079124
    PNX mean: 1.1571283635979368 median: 1.101026282853567 var: 0.3396081112907901
    TKR mean: 1.0642692665137068 median: 0.9652200900015517 var: 0.23503730398611777
    DDF mean: 1.2417013786504962 median: 0.9159779222441926 var: 2.054565354609836
    XCT mean: 1.5213308933486684 median: 0.9408450704225351 var: 13.427764768455699
    VISIO mean: 1.2716558949695407 median: 0.9950789205036256 var: 2.0481602919020565
    QBC mean: 1.545156671720086 median: 1.2225574847857454 var: 6.182650743761553
    ZZC mean: 4.957085579825731 median: 0.9158878504672896 var: 305.8714929882008
    CNO mean: 1.4898250366945687 median: 0.9699248120300753 var: 17.56973558469382
    NEWB mean: 1.2009486325219543 median: 0.9983735028833357 var: 1.216252953327545
    DRXNE mean: 1.2834076117312176 median: 1.0132640890266644 var: 1.8345395872407029
    HBC mean: 88.13480294953291 median: 0.7637735736495657 var: 93156.27500911307
    BITSILVER mean: 1.6453348003417172 median: 0.9968976215098243 var: 83.77159687454176
    NTO mean: 0.9339200452434482 median: 0.8220661398887912 var: 0.18916916949878473
    808 mean: 1.3664993476993688 median: 0.9831649831649831 var: 5.991010489269901
    CFD mean: 71.42990011139241 median: 0.9779580304433655 var: 110444.35357878619
    IRL mean: 1.1065209309423316 median: 1.0714285714285714 var: 0.16974574123771138
    SWING mean: 1.134636989011275 median: 1.0035098556747346 var: 0.39406338023252424
    KUSH mean: 1.1098358863438238 median: 1.0116471486761711 var: 0.275017337807499
    TOKC mean: 0.8666453155564047 median: 0.7815555754911636 var: 0.19998550892364608
    CASH mean: 1.672952566647201 median: 0.9520833333333335 var: 11.37666484168699
    DSR mean: 16.161247607906546 median: 0.9083474720582798 var: 5031.515176416436
    CCN mean: 1.10603553641896 median: 0.9812706364567916 var: 0.4305417299913498
    KAYI mean: 1.942646664916354 median: 1.0065512400561536 var: 18.64748393887246
    STV mean: 1.1764259754236417 median: 0.9873130088998295 var: 1.2839019162872904
    MARS mean: 1.1568601353256316 median: 1.0771899392888118 var: 0.7015025142139202
    XCXT mean: 1.144257640938871 median: 0.9316293162931629 var: 0.37609644037206014
    VUC mean: 1.1598183645908617 median: 0.9677154582763338 var: 0.9366231048031494
    XRA mean: 1.1251332294251566 median: 1.0167487684729062 var: 0.535861770013579
    HNC mean: 6.036719500461169 median: 1.052130740587505 var: 173.98031230806654
    POST mean: 1.0744377284333213 median: 1.0045489740611693 var: 0.1430093682485255
    ORE mean: 63.644138589970055 median: 0.7529691211401425 var: 31651.940336030617
    BOLI mean: 1.2405736413930986 median: 0.9840665319446604 var: 1.9727663879250554
    SDRN mean: 1.0433621797801809 median: 1.002111746590409 var: 0.20371275116210633
    NEVA mean: 1.1470464251993313 median: 1.0084337349397587 var: 0.44590367169808504
    BRIA mean: 1.3062692214775276 median: 0.9580419580419581 var: 3.458592601406887
    MAO mean: 1.0561573820997827 median: 0.9922294788664043 var: 0.18782121201289811
    GLT mean: 1.090840712501676 median: 0.9781623403378656 var: 0.3529084776378271
    CCT mean: 5.582036172265085 median: 0.8629501234647342 var: 534.5558325689586
    BITGOLD mean: 71.22110731604651 median: 1.0009301132172295 var: 1097297.3032010873
    BCF mean: 1.713598130799974 median: 0.9393863719452178 var: 20.57469605071968
    ATOM mean: 1.2672946523536366 median: 0.990108487555839 var: 1.4819382941624923
    PHS mean: 1.2269894772904069 median: 0.9969625301428306 var: 2.035409923930922
    GLC mean: 2.2751528897293074 median: 0.923814616372616 var: 306.02653793251983
    CHAN mean: 1.8166077003884864 median: 0.9386520465072313 var: 8.48081443233509
    LEA mean: 1.304474172919431 median: 1.0514950166112957 var: 0.8126726118656442
    HONEY mean: 19.413985105858327 median: 0.9672131147540983 var: 22911.187905992054
    ETHD mean: 1.1967045213724785 median: 0.9164239279071978 var: 1.0531134444108605
    AMS mean: 1.1708159792458466 median: 1.0041015124327097 var: 0.8493554614273484
    ONX mean: 1.2161296035968716 median: 0.9322763824840887 var: 0.9638577624745152
    PASL mean: 1.084916901326859 median: 0.9803925018821329 var: 0.31524425678139223
    AMBER mean: 1.0856058386759424 median: 0.9955836168542266 var: 0.3377328211268707
    INFX mean: 2.5236939188139274 median: 1.005456953642384 var: 113.95567893704083
    ECO mean: 1.0948861812440271 median: 0.9974381256559864 var: 0.6068537382016524
    QBIC mean: 17.191039569963216 median: 0.7784810126582278 var: 1900.5336680008636
    EMD mean: 1.1950020089673257 median: 0.9702127659574469 var: 3.0374826472880825
    RED mean: 1.1469868523342346 median: 0.9883313885647609 var: 0.8786941466307235
    COAL mean: 1.3112806253582907 median: 0.9555873225325612 var: 1.9018132055150019
    EOT mean: 2.585169122095874 median: 0.8731334988328578 var: 84.35125541302433
    BERN mean: 1.1331941701599806 median: 0.9619935460738613 var: 0.7644544184830999
    MAY mean: 1.2011475161422998 median: 0.9797421708940908 var: 1.328148806661042
    SHDW mean: 1.9531682636256547 median: 0.9601555679022143 var: 16.133261127940624
    ROOFS mean: 1.0585521509917541 median: 1.0789044550739035 var: 0.17941049004702456
    DALC mean: 25.521461678881533 median: 0.9350779598138458 var: 22396.06136955381
    DUO mean: 2.07236258438579 median: 1.0174826143573545 var: 101.64479298866526
    EAGLE mean: 1.1546883222251811 median: 0.9683223911541121 var: 0.741911368836474
    REE mean: 2.4720423538179572 median: 0.9175769782207961 var: 934.225131964482
    $$$ mean: 1.3979324845722374 median: 1.0288104089219332 var: 13.303922980805794
    RPC mean: 29.340631230822588 median: 0.9812830630909974 var: 232405.67418736793
    BIP mean: 1.1308914497906326 median: 0.9701340326340326 var: 0.4369526453845213
    TAJ mean: 1.1792683118867868 median: 0.9667519181585676 var: 0.7896363308654779
    SCS mean: 1.1227254000011258 median: 1.0808246188514488 var: 0.177310228861084
    POS mean: 1.2295303839719556 median: 0.9049773755656109 var: 1.1594260209036262
    LBTC mean: 3473.5766434162574 median: 0.9556636928899702 var: 101002607.86642481
    ATX mean: 1.1696174754960478 median: 0.9501718213058419 var: 0.9376129645376173
    FNC mean: 1.5234362515110502 median: 0.9264027992097735 var: 9.989984914517066
    PCN mean: 3.9771705461100946 median: 1.0068493150684932 var: 184.87435979540678
    ZCG mean: 935.1152315446701 median: 0.8613190803321978 var: 19179263.9551275
    BITEUR mean: 1.0538168596351642 median: 1.0089285714285712 var: 0.40039859074692385
    DIX mean: 33115.40837597554 median: 0.832442842942346 var: 102936929889.00764
    CNNC mean: 61.08201687077794 median: 1.0883273497192303 var: 208791.2599689531
    MDC mean: 1.411089642969995 median: 0.8745021704959156 var: 2.6074979559666627
    CPN mean: 1.0315371031320077 median: 0.8932038834951457 var: 0.8363014822697094
    ERY mean: 1.1654152305299745 median: 0.9449845815410602 var: 0.577769033442615
    SH mean: 1.2836590331198081 median: 0.9862068965517242 var: 1.2854280503703832
    BNX mean: 1.161983044925661 median: 0.9752380952380952 var: 0.8786935732318215
    XBTS mean: 1.2047829076035945 median: 1.051267148152394 var: 0.9797283044402221
    WOMEN mean: 1.0826567771218767 median: 0.9196334155798377 var: 0.3929222145776209
    MSCN mean: 13.4821149215068 median: 0.942261427425822 var: 1533.5098041313386
    KRONE mean: 1.333085771929597 median: 0.9065404700610755 var: 1.7000690265992475
    SLEVIN mean: 1.236028399490155 median: 0.9576185671039354 var: 0.7932123043162267
    LTCU mean: 4.294298689305265 median: 1.005028922820366 var: 356.0160723308599
    VPRC mean: 1.6243473959662376 median: 1.0999999999999999 var: 7.236927212539622
    QCN mean: 42.38509865009245 median: 0.986161524905993 var: 456474.48823623854
    ACP mean: 1.5650010827732304 median: 0.975062344139651 var: 32.487592290770884
    EXN mean: 1.136656576772646 median: 1.0217973697028737 var: 0.3213918152817941
    SANDG mean: 1.2066726498426874 median: 1.0161278863232681 var: 0.9747390321690782
    LIR mean: 1.0840133912907293 median: 0.9779359430604982 var: 0.598494494047768
    BOAT mean: 1.2886977270994755 median: 0.9420437214031521 var: 1.322970351105315
    GEERT mean: 1.191733017996405 median: 1.0164835164835162 var: 0.6561572232787363
    PLNC mean: 1.0889489500826908 median: 0.9759903961584635 var: 0.6942759119672509
    XRC mean: 1.212179218560495 median: 0.9482059282371297 var: 0.688619509511956
    ALTCOM mean: 4.554315208318427 median: 0.9395517705064993 var: 298.5416308779701
    VRS mean: 2.665957615847634 median: 0.9562227668845316 var: 489.8052149423505
    GBC mean: 393.7801281667379 median: 0.9274902343750001 var: 24381688.236355904
    TOR mean: 58.52724979777714 median: 0.9217145279770197 var: 203402.4556356636
    VOLT mean: 1.0522272596024007 median: 0.9728155339805823 var: 0.1792763864115178
    ULA mean: 3.381578537132415 median: 1.0049056431044299 var: 85.91292313779186
    CONX mean: 1.1162724900172973 median: 0.9801276949511483 var: 0.35241024069618454
    COUPE mean: 1.9454679441349632 median: 0.9285714285714285 var: 11.544182939046285
    VLTC mean: 1.889015703726581 median: 0.9496541122213682 var: 17.29888257593867
    NANOX mean: nan median: nan var: nan
    PRC mean: nan median: nan var: nan
    EXRN mean: 1.353533361181997 median: 1.0416666666666667 var: 1.2227248442467247
    LVPS mean: 89.22517272274904 median: 0.8734935610495145 var: 542196.0958508498
    TSTR mean: 1.2162746548330794 median: 0.8943101799530557 var: 2.5980145470711595
    DMB mean: 1.2709879593767064 median: 0.9896874999999999 var: 1.137179744834215
    PAC mean: 1.2967258731477012 median: 1.0147058823529411 var: 2.5488675883883762
    HDG mean: 616.2859524078818 median: 0.9868708971553609 var: 9761625.883855678
    ECOB mean: 1.010852541433867 median: 0.9672364132494504 var: 0.12586282801039753
    PLU mean: 2.192068733838615 median: 1.0048309178743962 var: 103.79860900214682
    XNN mean: 1.041775092770566 median: 0.9152332220226839 var: 0.21100719684712263
    AC mean: 1.2130475261767741 median: 0.9836244541484715 var: 2.288808576586213
    BASH mean: 1.1853743306821776 median: 0.9806523115896135 var: 0.7153258535961594
    ETT mean: 1.7600942065947989 median: 0.9560652281871712 var: 25.563969381358977
    AHT mean: 1.3170304050999886 median: 0.9618867557801553 var: 1.6993690763514064
    BBT mean: 1.177619875625489 median: 0.9553054424720342 var: 0.7463152632676852
    REX mean: 1.1226867761119252 median: 0.9085969930957349 var: 0.3739562386160471
    PGL mean: 1.0279342522467583 median: 0.8761550219154591 var: 0.1715578395796959
    YASH mean: 1.624321663300191 median: 1.0414606537856552 var: 16.981058301486367
    PRIX mean: 1.3710810060245868 median: 0.9980353634577603 var: 1.5086225171957626
    DAR mean: 1.234201627860035 median: 0.9939220650285431 var: 1.8005362534868494
    CBX mean: 1.1173434643237194 median: 1.0013241802278983 var: 0.9902053568074782
    RUSTBITS mean: 1.14933303405716 median: 1.0096482319268767 var: 0.7145811987231977
    PIPL mean: 1.0530787301095441 median: 0.9115436279973705 var: 0.15854867185382962
    LEAF mean: 1.5482930459671738 median: 1.1428571428571428 var: 10.495514010374428
    VTA mean: 2.4674943624055454 median: 0.9333333333333335 var: 284.336998590829
    V mean: 1.2074659876338674 median: 1.0310463499813514 var: 0.9211399661455336
    AU mean: 1.290164377923971 median: 0.927608810716176 var: 9.617449284193372
    ESZ mean: 0.6956590611458836 median: 0.877847052789176 var: 0.11636453911949185
    RNS mean: 1.5665432063134825 median: 0.9553081205605684 var: 9.757917031876792
    SHORTY mean: 1.1069802347570346 median: 0.99087105363256 var: 0.21539262738940287
    RIYA mean: 1.8905051390690721 median: 1.0487834668751224 var: 23.45409562659829
    INPAY mean: 1.0354864309192933 median: 0.9998074916786727 var: 0.11917079493740337
    LOG mean: 1.0700775152116189 median: 1.0086669418076764 var: 0.18354014537561728
    FLT mean: 1.1130525536725802 median: 0.9923896499238963 var: 0.912381051564618
    UNI mean: 1.323009346552254 median: 1.040006038647343 var: 1.81879128851006
    SDC mean: 1.13321311894872 median: 1.0122088815089199 var: 0.6209474675866654
    I0C mean: 1.2173310280258212 median: 0.9956453256740478 var: 2.9186505880572073
    FCN mean: 1.1665044475764246 median: 0.9815829861872397 var: 2.240188343970634
    BPC mean: 1.1865782125929716 median: 0.9599165429522931 var: 1.4205238229919068
    SUPER mean: 1.7313326648943297 median: 0.9896661367249603 var: 3.6173434762046544
    USC mean: 1.1388434996420387 median: 1.041833905774265 var: 0.30574067028371904
    HTC mean: 1.0904812683838856 median: 1.012820512820513 var: 0.4974447760374398
    FIMK mean: 1.0865355250465218 median: 0.9585301837270342 var: 1.8445168599738153
    EBET mean: 5.86132797089874 median: 1.016249803983064 var: 655.6225602155197
    METAL mean: 1.0930275608832771 median: 1.0140449438202248 var: 0.2603364007263204
    GRIM mean: 1.2252908389896917 median: 1.0361990950226243 var: 0.6223435007891208
    NDC mean: 1.5910943908286277 median: 0.9311313932092607 var: 14.322520265406355
    SCORE mean: 1.2874188666435746 median: 0.939118582462517 var: 1.282986341404475
    HBN mean: 1.1805606573168723 median: 0.969379460716926 var: 3.2251239935088916
    LNK mean: 32.8532562429677 median: 0.9957675512260665 var: 44333.5278703335
    MBI mean: 1.0041123288557106 median: 0.9637243415146305 var: 0.08611588090924406
    HODL mean: 1.1418649012228965 median: 0.9473180076628354 var: 0.6985764157289163
    UNIC mean: 1.4041761700295128 median: 1.0359565807327 var: 17.397494998832762
    ELE mean: 1.2551123485879179 median: 0.9263732862675556 var: 1.700343586835064
    SMC mean: 1.238605605777706 median: 0.9752475247524752 var: 2.8576313989570705
    ITT mean: 1.3841831742400919 median: 1.0320426739852482 var: 3.220725485484285
    BITS mean: 1.1402515169307632 median: 1.00109362369835 var: 1.1038447368501696
    TRI mean: 1.3597885840710486 median: 0.9598334323608496 var: 4.701134593710961
    OPAL mean: 1.041137386719177 median: 0.8478208693933449 var: 0.47184657330950747
    HAL mean: 1.0990137750306581 median: 1.0053276505061268 var: 0.557637810259712
    NYAN mean: 1.7642606120567026 median: 0.9629629629629629 var: 86.02314704666438
    FC2 mean: 2.732455662251869 median: 0.9668638545953361 var: 698.0896254941811
    ARG mean: 1.211521641069712 median: 1.0005227562322345 var: 3.200446446699671
    WGO mean: 1.1327559283353947 median: 0.9978490418459132 var: 0.5679726034041624
    FLY mean: 1.1650963015838032 median: 0.9844961240310077 var: 0.8700002578216083
    TALK mean: 1.1116048906919214 median: 0.7390376866556057 var: 8.71077517712459
    PXC mean: 1.094766318097766 median: 0.9608695652173914 var: 0.6882922048973388
    VAL mean: 2.9361145425157265 median: 1.0681818181818181 var: 182.8970261697476
    BLC mean: 4.267039280361162 median: 0.9777468706536857 var: 2916.4912920153333
    DTC mean: 1.2384566308252343 median: 0.8984881209503239 var: 10.602451368267207
    XGR mean: 1.1200538018145074 median: 0.9925742574257426 var: 0.3269347758691268
    BIGUP mean: 1.0778910156922006 median: 1.0185185185185184 var: 0.48578957119856775
    WAY mean: 1.078206327610003 median: 1.022517911975435 var: 0.151897295943935
    SIGT mean: 1.3764876895665055 median: 0.9052266319670352 var: 6.597284220877631
    BTCR mean: 1.143899623061239 median: 1.0214477211796247 var: 0.36818731934219545
    TRK mean: 1.111582593902206 median: 0.9738593018090893 var: 0.573998833891147
    TGC mean: 1.7271789742472727 median: 0.9868995633187773 var: 54.27022348899906
    XJO mean: 1.3063228520062848 median: 0.9864682002706361 var: 14.087582134375538
    MOTO mean: 1.7771481004472303 median: 0.9430379746835442 var: 15.03844397104057
    GAP mean: 1.1518955720645092 median: 1.0010963582151873 var: 1.1336191769957014
    BLOCKPAY mean: 1.1057133691839574 median: 1.0270158132794147 var: 0.2914441531552443
    CRX mean: 1.341200254747452 median: 1.0579710144927537 var: 2.3625752039914176
    TSE mean: 2.2791371766027138 median: 0.9940520446096655 var: 84.81250814043386
    CV2 mean: 1.3795684959523176 median: 0.8571428571428571 var: 2.98218415626902
    BUCKS mean: 2.800425300369064 median: 1.0024165856818918 var: 364.43928838385796
    B@ mean: 1.0380915165258084 median: 0.9530201342281879 var: 0.35653376645381274
    CHESS mean: 1.177279577916356 median: 0.979989468141127 var: 1.0423759958208179
    MNM mean: 1.1240401903209452 median: 0.975598404255319 var: 0.4479402094316618
    PR mean: 1.3307795392254695 median: 0.9766330323951142 var: 13.544030730056974
    MAD mean: 1.1619855969590314 median: 1.0833333333333335 var: 1.5666897456918507
    BITZ mean: 1.6149837639815483 median: 1.037584323803405 var: 10.576608340798742
    C2 mean: 1.094957851906991 median: 0.992988606485539 var: 0.37526618099768444
    PX mean: 1.3167183160075466 median: 1.0096027935399388 var: 2.2935060426359613
    AMMO mean: 1.2454719793432256 median: 1.008 var: 1.0327427493430121
    DSH mean: 120.78772887471686 median: 0.9957805907172996 var: 1766318.6323125102
    FUNC mean: 1.1974670596902068 median: 0.9981040384627827 var: 0.8808882246516265
    RBIES mean: 1.0978952417407788 median: 0.9962592564317887 var: 0.4604946937779428
    XRE mean: 1.1496438322116296 median: 0.9543269230769231 var: 0.5979597163288038
    VC mean: 1.6777454391524351 median: 1.0071050986187688 var: 4.844663577068805
    EVIL mean: 1.227795811347614 median: 1.0272473718086248 var: 0.8743319922877909
    LTB mean: 1.5670240490273648 median: 0.9700075334295939 var: 27.027151581800496
    XVP mean: 1.1025067031316667 median: 0.9956256790590012 var: 0.371851932032854
    888 mean: 1.0820263426743875 median: 0.9311926605504587 var: 0.5591012643961407
    UNITS mean: 6.0985243598078185 median: 0.9256703714415566 var: 1525.772507720764
    TEK mean: 1.1089249912011714 median: 0.9756097560975611 var: 1.8123522843921376
    NUKO mean: 13.24514940451393 median: 0.8413037890082772 var: 2436.8235033737674
    SPEX mean: 0.9773693662767596 median: 1.037037037037037 var: 0.11208856834431094
    ISL mean: 2.705968167046168 median: 0.9983680130558955 var: 340.35517620840267
    CCO mean: 1.4017406689657235 median: 1.1606548111665085 var: 2.1151413839889295
    FRC mean: 1.1757156999741698 median: 0.9828823854224187 var: 2.2855174574658084
    SCRT mean: 1.0761498638676268 median: 1.0176325247079963 var: 0.1864669176370532
    PXI mean: 1.1676185212779713 median: 0.9957805907172995 var: 0.6023026728814825
    XIOS mean: 2.8993969445993257 median: 0.999251605243554 var: 80.0910647845231
    DLC mean: 1.322828441241579 median: 0.9931899867583074 var: 4.338456194507949
    QTL mean: 1.081722764693744 median: 0.9690309690309691 var: 0.2714017317242946
    BSTY mean: 1.2186052785875099 median: 0.9939046253137324 var: 4.627346893726443
    SPACE mean: 1.4862549356283312 median: 0.9784946236559139 var: 6.066200144894349
    BUMBA mean: 1.2275057848340591 median: 0.9966114457831325 var: 1.7337949075240093
    J mean: 1.2376218198482425 median: 1.0056711471183941 var: 2.794134516924475
    IMS mean: 1.1808634837583023 median: 0.9926605504587156 var: 0.8504630271572329
    CON mean: 1.4029374417066132 median: 0.965789828438661 var: 3.689281484102817
    SOON mean: 1.4139123686783246 median: 0.9909090909090909 var: 6.382715583911948
    611 mean: 1.1825018063535924 median: 1.0080609046126285 var: 0.5581454748198882
    IMX mean: 1.153093210566929 median: 0.9357798165137614 var: 0.48424765147798593
    KED mean: 1.096569774478257 median: 1.0224661544090743 var: 0.1609433214794547
    MST mean: 1.3161685301947181 median: 1.0297629143613833 var: 4.5004558122804115
    ACOIN mean: 1.1906825514487978 median: 0.9525201612903225 var: 1.6704330588963308
    FIRE mean: 1.1923657429122636 median: 0.701548215010534 var: 3.976500257584937
    ICOB mean: 1.1511612549232617 median: 1.0126582278481011 var: 0.8489731674559929
    VLT mean: 1.2085301764362284 median: 0.9906906148560848 var: 0.9469598696887085
    EVO mean: 1.672744402097316 median: 0.9787100814026299 var: 11.293726457709171
    XNG mean: 1.2482744600744093 median: 0.9952054495143249 var: 2.4717728371546577
    VOT mean: 1.1412478823371197 median: 0.8504014204947765 var: 0.7822859856343883
    ZUR mean: 1.7075212247819926 median: 0.983667409057164 var: 23.53621980261253
    XBTC21 mean: 1.2264242067190851 median: 1.063054187192118 var: 0.8011473147058402
    EUC mean: 1.5681977990271638 median: 0.9684343434343435 var: 28.588045520406542
    CACH mean: 4.390002712193513 median: 1.1134328358208954 var: 2852.1599114546766
    300 mean: 495.4176278532174 median: 0.9391517930243981 var: 10656486.661135728
    YAC mean: 1.102577118392193 median: 0.9658391915641478 var: 0.9425625723020383
    ASAFE2 mean: 402.0478745800165 median: 1.0833333333333335 var: 14920665.403036142
    BOST mean: 1.1098779396039817 median: 0.9733570159857903 var: 0.5236845159906283
    BRAT mean: 1.1794298517449313 median: 0.9753694581280788 var: 0.6973084287729491
    MNC mean: 1.9965902620128446 median: 0.8173836698858649 var: 279.8376700743839
    ADCN mean: 1.181048014551353 median: 0.9481415562401326 var: 1.6596438120407389
    JIN mean: 1.338783234601419 median: 0.9800559076303272 var: 2.627302262367394
    GPU mean: 3.148249430188154 median: 0.9828669331810393 var: 145.5165260461097
    BTPL mean: 1.4368557280417538 median: 0.9709571469211472 var: 6.061191600202726
    LUNA mean: 1.1284800616748791 median: 0.9874871603324307 var: 0.4433121496309185
    FRK mean: 1.161468380294946 median: 0.9881658566598974 var: 1.4178328270073357
    FUZZ mean: 1.2169058887127635 median: 1.0480176211453744 var: 1.2802116775084267
    XCO mean: 1.157403634813355 median: 0.9974905897114179 var: 0.922893495414793
    YTN mean: 7.34222730519194 median: 0.8025662525267638 var: 536.2819963000296
    ALL mean: 1.8802982985417784 median: 0.9711812443642921 var: 27.325657728032763
    SOIL mean: 1.1644421010265615 median: 0.9020800627943485 var: 8.632440815647906
    CTO mean: 1.2354850965618611 median: 1.0254237288135595 var: 1.1567124721634126
    HMP mean: 1.1543637310659822 median: 0.9734513274336284 var: 0.6793505991688626
    ANTI mean: 1.204689862079769 median: 1.0237099023709901 var: 1.7262694045116516
    ELC mean: 1.668344734070042 median: 0.9736143945363802 var: 56.38843258557082
    OFF mean: 1.5654712163708095 median: 1.0963414634146342 var: 1.3067839770201655
    NRO mean: 1.0630893118054838 median: 0.8817578248498262 var: 0.3976479303473105
    WARP mean: 1.353426306798839 median: 0.9936029715229053 var: 3.402011245854155
    JS mean: 1.2330127337791412 median: 0.8608055709424706 var: 0.7607849172646576
    XCRE mean: 1.2128311605137645 median: 1.0309218203033839 var: 0.7856357994311977
    BSTAR mean: 1.2554374556122645 median: 1.0379746835443038 var: 2.534434039659976
    FLAX mean: 13.028993431800254 median: 0.985445836403832 var: 25063.527776267943
    GP mean: 1.1143955067409013 median: 0.9826535732205577 var: 0.4067682843815012
    BLN mean: 1.228414288099157 median: 0.915039111784002 var: 2.4641061192182496
    STARS mean: 3.7327598921434255 median: 0.9266129476515041 var: 157.56462139208665
    TRDT mean: 1.2221525853780626 median: 0.8766519823788547 var: 0.9223179441636847
    BENJI mean: 1.866415286284369 median: 0.9731800766283524 var: 44.9309333372485
    MAR mean: 4.314852695191462 median: 0.9890876742117227 var: 109.73332182511542
    GPL mean: 1.1919269563711739 median: 1.0017030524178985 var: 0.8809678697271112
    SPT mean: 1.5413164050385812 median: 0.9246658246500369 var: 33.739080392152324
    DRS mean: 1.049851281588208 median: 0.9790209790209788 var: 0.2877609872402751
    DBTC mean: 1.2077401113716488 median: 0.9951923076923077 var: 0.7183993708334779
    BTQ mean: 1.331399099625816 median: 0.9786585365853658 var: 7.656226715979057
    SONG mean: 1.1358067421644724 median: 0.9842931937172775 var: 0.5478386247294623
    CXT mean: 1.3454510552956327 median: 0.9214133414559854 var: 3.15323014146288
    LTCR mean: 1.2223800231192608 median: 1.036478745854688 var: 1.1040522253114722
    BLRY mean: 1.1125137496236321 median: 0.9802259887005648 var: 0.38815550342261557
    BXC mean: 1.1574674000512766 median: 0.9308398023994353 var: 1.348933727513252
    SFC mean: 1.1654615373359136 median: 0.9656862745098039 var: 1.016927681167494
    BAS mean: 1.3712859949111935 median: 0.8429584273283918 var: 2.5979253729007965
    RBX mean: 1.1515477682170179 median: 0.9293078055964653 var: 0.6630588745091691
    CF mean: 1.8228468848893342 median: 0.9847195430992097 var: 56.992182413389074
    MTLMC3 mean: 1.1717937672277312 median: 0.9756097560975611 var: 0.7513706807918317
    VEC2 mean: 1.8732623751401543 median: 0.9823255813953489 var: 56.93074572020321
    ICE mean: 12.678486420415252 median: 0.9723016452508819 var: 6759.692576933875
    MND mean: 1.2267088577161167 median: 1.0018975332068314 var: 2.9832266659325604
    PONZI mean: 1.5978976631852118 median: 0.9682926829268292 var: 8.052455047088454
    PRX mean: 1.2681200174820415 median: 0.9831570701135919 var: 1.1452500239220031
    PEX mean: 1.5501512722429032 median: 0.9682267067410907 var: 23.50385487908452
    WBB mean: 1.1799603990221716 median: 0.9834194326723791 var: 1.0361748843999612
    SOJ mean: 1.744679812637328 median: 0.83700636615305 var: 12.508803758000136
    ZYD mean: 1.044984190811986 median: 0.9845751633986928 var: 0.17538373432943916
    NTWK mean: 1.2649928838575364 median: 0.8201658664338716 var: 2.0327045477468926
    DLISK mean: 1.110106870249831 median: 1.0270270270270272 var: 0.5749181370064065
    URO mean: 2.8754470979015045 median: 0.9574091574480701 var: 829.1389750623312
    WORM mean: 1.177185818173936 median: 0.931736526946108 var: 1.8674612587455481
    MILO mean: 1.41490022548807 median: 0.9879557291666666 var: 3.3599004858014037
    JOBS mean: 1.2224336849906101 median: 0.9655172413793106 var: 2.5798882626830846
    VIP mean: 1.0928796789020403 median: 0.9741379310344829 var: 0.30125944581965897
    CAB mean: 1.3529926821464715 median: 0.9685230024213075 var: 4.609523789330317
    ICON mean: 1.264301070350909 median: 1.0228445908841295 var: 1.6090405412148507
    ORLY mean: 1.0497634899370316 median: 1.004100761570006 var: 0.15329609568105368
    JWL mean: 1.1074540431876632 median: 1.0070689478537034 var: 0.5968566731675905
    URC mean: 1.3787742528202764 median: 0.9847343781803379 var: 3.8496713758591787
    RIDE mean: 1.0852462112328451 median: 1.0316091954022988 var: 0.22511552476257246
    UET mean: 2.80078682386843 median: 0.9145170059807888 var: 109.38553054715005
    EGO mean: 1.0808021161598202 median: 1.0434782608695652 var: 0.2123275683726981
    ZMC mean: 1.2812342730683781 median: 1.095779220779221 var: 0.3227808839387851
    DRM mean: 3.4101574736484888 median: 1.2140707298720845 var: 1246.731820844547
    PULSE mean: 1.2448610930058641 median: 0.9980676328502417 var: 1.8009509452031385
    ARB mean: 1.5339553109472246 median: 0.9663064208518753 var: 34.69228328633172
    CESC mean: 1.0639381254537026 median: 0.987012987012987 var: 0.2330433303636608
    COXST mean: 3.2271590396372045 median: 0.9808219178082193 var: 324.76787170704165
    BSC mean: 1.3328900439937676 median: 1.027346387575962 var: 5.6581212254412
    STEPS mean: 1.0950171757694227 median: 0.9825581395348836 var: 0.35517728327573245
    PLACO mean: 1.177034240768837 median: 0.8797338792221086 var: 1.327252795540585
    IMPS mean: 1.1918040293691146 median: 1.0560398505603987 var: 1.2560294716388207
    CWXT mean: 1.0692387959190262 median: 0.9971305595408895 var: 0.23627019074803696
    G3N mean: 1.405427213598226 median: 0.9957173447537474 var: 10.556395721643794
    TAGR mean: 1.1066909635413396 median: 0.9784379492093913 var: 0.5351871172972417
    RSGP mean: 380.72903615565457 median: 0.9787028073572119 var: 6370966.063228622
    BIOS mean: 1.3410956431210117 median: 0.9260767088065137 var: 19.16499649364641
    ZNE mean: 1.156930638413556 median: 1.0037795275590553 var: 0.7185112725662267
    PIE mean: 2.6510922722278543 median: 0.9690721649484536 var: 139.15175483679278
    CRT mean: 3.2691881453636795 median: 1.0023474178403757 var: 529.3287748903493
    BRAIN mean: 1.237309169399017 median: 0.9899999999999999 var: 1.523562351145926
    OS76 mean: 1.2631170618973884 median: 0.9964745284681826 var: 1.1859600900877698
    DES mean: 1.2161070201012911 median: 0.9640479360852197 var: 2.194040065574004
    XOC mean: 1.1266554579439532 median: 1.0108202503038914 var: 0.43651574283553235
    SDP mean: 1.2129580039257153 median: 1.007292495359321 var: 1.5389496250214174
    HVCO mean: 1.1445380862911616 median: 0.9850696471082023 var: 0.5788899666275382
    IBANK mean: 1.1103885024483262 median: 1.014360162130863 var: 0.33623938142948406
    AGLC mean: 1.6828368601547086 median: 1.0743609604957398 var: 2.926503065653236
    CRDNC mean: 10.009983817443823 median: 0.8727919337189308 var: 1858.4113399796734
    DOLLAR mean: 1.1085876797689864 median: 1.0151397213357205 var: 0.2835969431450981
    ARGUS mean: 6.2224530357290195 median: 1.0343038562800062 var: 205.02030894932628
    CTIC3 mean: 30.06299311179085 median: 0.9982920580700256 var: 21691.477042863233
    BIOB mean: 1.1041867413529651 median: 0.9884947920212404 var: 0.29149611917125684
    P7C mean: 1.2942495773789118 median: 1.0555555555555556 var: 7.281470946654378
    CREVA mean: 1.3274356611052016 median: 0.9441340782122903 var: 3.9649248649260787
    SOCC mean: 4.008277692096764 median: 0.9676224493170619 var: 403.4049735628667
    ELS mean: 1.335507337583955 median: 0.9568403908794789 var: 2.3254810031722664
    ALTC mean: 1.3272824094710127 median: 1.023391812865497 var: 7.193902890442112
    FXE mean: 38.72958588172604 median: 0.9901960784313726 var: 65453.634263856926
    TYCHO mean: 1.0320306609156107 median: 0.9308203055458482 var: 0.16220355961018681
    CTIC2 mean: 1.1475321386416597 median: 0.957561468507915 var: 0.5821832760730874
    NODC mean: 1.096976423042292 median: 0.997844827586207 var: 0.2581175499555406
    SLFI mean: 2.1268040645990007 median: 1.0833333333333335 var: 243.45402296586806
    MGM mean: 2.3525222918173645 median: 0.9399718931941378 var: 93.13344472207137
    GSR mean: 1.5752438595820981 median: 1.0098954137291827 var: 4.499874582121238
    CALC mean: 1.2107056500796387 median: 0.988716320576626 var: 0.9109456715247694
    CCM100 mean: 1.200523925203136 median: 1.0204800296543417 var: 0.9710748959616553
    PIZZA mean: 1.537108808602066 median: 1.0289855072463767 var: 7.442467257362914
    DGCS mean: 1.3728924669701048 median: 0.9903381642512078 var: 7.468323755030703
    ABN mean: 84.22613745375288 median: 0.976527940778189 var: 537135.2011552986
    DIBC mean: 1.4810178723572207 median: 1.0180180180180178 var: 13.614502587786843
    EBT mean: 2.110650209114828 median: 0.9251570132588974 var: 32.47735387041713
    HT mean: 580.1102914050056 median: 1.0460526315789473 var: 648275.5978998177
    ATMC mean: 1.0487550050538224 median: 1.0689655172413794 var: 0.026730263445658136
    BCD mean: 1.7701572266210557 median: 0.889418795206347 var: 11.255421288144811
    ELA mean: 2.015631458941626 median: 1.15990990990991 var: 4.448793733820546
    EPC mean: 0.8395667795683502 median: 0.9947048795242249 var: 0.13478908698479553
    EKT mean: 1.052161162262674 median: 1.1158083547273747 var: 0.019055790828440344
    NCASH mean: 0.5101655162303957 median: 0.21431338773223343 var: 0.13129272290533972
    IHT mean: 3.288921282798834 median: 3.288921282798834 var: 0.0
    OC mean: 0.878136921721735 median: 0.9461229166565674 var: 0.1469388165274463
    RUFF mean: 2.9829377488076143 median: 1.045800653044737 var: 12.93618565722093
    AIDOC mean: 0.9979641156586496 median: 0.9454717696097006 var: 0.08746586195864979
    WIC mean: 19.279165775281253 median: 1.0239645775371031 var: 1318.7789851136351
    AUTO mean: 0.057410034327737766 median: 0.057410034327737766 var: 0.0
    NKC mean: 1.312675734854822 median: 0.9290431541552617 var: 0.5861768755719653
    TOPC mean: 1.0049155976783817 median: 0.8414390406395735 var: 0.12824590355395468
    CHAT mean: 1.9339351985986504 median: 0.9904220760934079 var: 6.68360509622283
    AAC mean: 0.9723823613931656 median: 0.9545304026361076 var: 0.009764455145768661
    MTX mean: 1.606826375903898 median: 0.8740028037383177 var: 3.7697591390566725
    SMT mean: 1.0064456041786305 median: 0.8930933500049357 var: 0.4070675893751631
    BKX mean: 6.51442548335265 median: 0.9267015706806283 var: 287.7299092351945
    LIGHT mean: 0.8560230924918697 median: 0.8165318957771788 var: 0.1347385325064003
    BCX mean: 2.1717924585326314 median: 0.930304972982874 var: 23.94773058710399
    RKT mean: 16.67542914604741 median: 26.750039701445136 var: 152.246666764397
    W3C mean: 0.3736229844004757 median: 0.5913252288758818 var: 0.07583082759940717
    GNX mean: 10.334468492594295 median: 0.9295643926061231 var: 1206.5410279043003
    AVH mean: 0.6735029792012781 median: 0.8948049778668671 var: 0.1224783393424578
    PXS mean: 30.45172375137703 median: 1.0742574257425743 var: 5417.603989870385
    HLC mean: 0.8309781677010396 median: 0.8869575149718467 var: 0.05898740940797771
    OF mean: 0.9156339643504836 median: 0.9456112008616048 var: 0.15633302390075732
    MOF mean: 13.522614180991901 median: 1.0299491892279116 var: 1152.4768081620762
    CFUN mean: 0.8028232835387382 median: 0.8334452903418422 var: 0.040910766858308606
    REN mean: 1.9282480628057532 median: 1.0147860836859428 var: 1.294497053865199
    SHOW mean: 0.7801409730291327 median: 0.8385084925690021 var: 0.055257060077194685
    SSC mean: 5.6570140843319585 median: 0.8924418867685514 var: 171.1596003528458
    UBTC mean: 339.65818833710637 median: 0.8887509872503667 var: 1652596.7556627272
    RCT mean: 0.8214304943351421 median: 0.7693677856942845 var: 0.12982905596584307
    RFR mean: 0.33643542210421695 median: 0.3283726904996173 var: 0.0027953285598958295
    MLM mean: 1.2276746369698834 median: 1.0244716351501668 var: 0.17515298783419322
    UGC mean: 1.1818770679123995 median: 0.9236143747845975 var: 0.36549122233037395
    AWR mean: 0.9217816973923628 median: 0.9212451664450402 var: 0.03218393765680938
    PRS mean: 4.547389524739985 median: 0.9523946998193183 var: 89.3219658209343
    YEE mean: 0.8893185431249583 median: 0.9119551484523057 var: 0.17661285494922058
    XTZ mean: 4.447884447074542 median: 1.0145228215767634 var: 333.94027189554436
    KCASH mean: 0.8542851404699127 median: 0.9553894710953831 var: 0.07460800583212955
    GEM mean: 0.5623148930177772 median: 0.560579433941941 var: 0.05299173474836246
    STC mean: 1.3454366208077428 median: 0.9802275255726491 var: 1.1210706997778375
    FRGC mean: 2.0615749730898036 median: 1.003968253968254 var: 89.8861533689652
    BOS mean: 1.003936334139191 median: 0.9218963021687296 var: 0.21219912663167215
    UGT mean: 1.0420264582573642 median: 1.014090334838261 var: 0.055424227786637935
    REF mean: 2.40411535890598 median: 0.9355503995875225 var: 8.350684826274103
    MAN mean: 0.8754412546890937 median: 0.7786259541984732 var: 0.2434095994673499
    MGC mean: 1.0558182334720398 median: 0.9499205586655985 var: 0.253924534666487
    WETH mean: 495.91121780566635 median: 0.9278211845197075 var: 2153995.9953780584
    MOAC mean: 0.9477696860172151 median: 0.9636127355425601 var: 0.1436985827375577
    TKY mean: 0.7834028749871091 median: 0.8671503134950597 var: 0.20511903123189967
    SEXC mean: 1.0110416305566303 median: 0.8722923629162024 var: 0.150739453453942
    READ mean: 1.2002823234988897 median: 0.9932127147150733 var: 0.5502700787402881
    SBTC mean: 473.0877254381618 median: 0.8682944876063632 var: 3210943.2597458167
    INF mean: 0.9781161695463229 median: 0.9467239807216362 var: 0.1172463435647983
    IQT mean: 2.5665732469744804 median: 1.066958039714018 var: 79.44252615062615
    DDD mean: 1.224582708121945 median: 0.9981426209443646 var: 0.5186550145543057
    LCC mean: 8.511190465602695 median: 1.2861635220125784 var: 79.22922556074319
    BIG mean: 0.9653644499274611 median: 0.9150943396226415 var: 0.06310769834932986
    UIP mean: 0.7863908955560707 median: 0.9048964640801376 var: 0.10838750401251507
    QUBE mean: 1.052512577012139 median: 1.0170414773522711 var: 0.08326254594066648
    HPY mean: 1.0536505012621578 median: 1.0125762058185912 var: 0.12201393250209559
    CMS mean: 1.9603183874689163 median: 0.9537366548042705 var: 78.40299310370186
    BLAZR mean: 1.4332404976127682 median: 0.9096267190569743 var: 3.9163992550876134
    SETH mean: 239.43135054246162 median: 239.43135054246164 var: 8.077935669463161e-28
    MWAT mean: 0.6170754282396248 median: 0.9579373709674879 var: 0.2378928307172775
    BAR mean: 8.553178654269503 median: 0.7640403225806452 var: 472.537842346754
    VLC mean: 1.2740900162016213 median: 0.9317421552732571 var: 0.7540258632356786
    LYM mean: 0.31799903490429465 median: 0.31799903490429465 var: 0.0
    BEE mean: 10.909808956849929 median: 10.909808956849929 var: 0.0
    FIL mean: 3.585922246420982 median: 0.9389051808406648 var: 97.55678133038704
    XIN mean: 4914.286259676418 median: 0.870660775841142 var: 361521739.89747864
    EXY mean: 14.742461117957884 median: 24.04169058870291 var: 129.7135031243592
    ATN mean: 1.2057380708626086 median: 0.9447852760736197 var: 0.36625256160110325
    BSR mean: 0.9785414962695551 median: 0.9775049712770659 var: 0.07900231602574476
    XNK mean: 0.5616419454984476 median: 0.5616419454984477 var: 1.232595164407831e-32
    SWTC mean: 0.8491133296892642 median: 0.930298013245033 var: 0.06006819072611249
    IDT mean: 1.9613065163730243 median: 0.9962336654324287 var: 7.903632359098747
    INSTAR mean: 2.6077485607592963 median: 2.6077485607592963 var: 0.0
    BCDN mean: 1.0057692180604827 median: 0.9720653628118296 var: 0.08050585445340437
    TDX mean: 5.6271817575441245 median: 5.6298891433290175 var: 22.924547201952258
    FOTA mean: 0.7919963295678253 median: 0.8911915565200237 var: 0.05760812807897128
    ANI mean: 1.517004787604104 median: 1.4287909836065575 var: 1.287961512265099
    ADK mean: 3.149633639535992 median: 1.0832313943232263 var: 191.07486005388972
    IPC mean: 0.863420358585703 median: 1.0046353139061057 var: 0.13154275306336852
    NTK mean: 0.6346285417020118 median: 0.4754743375673366 var: 0.10594412427590601
    ECH mean: 1.9670121524043394 median: 2.425213118931165 var: 0.45041014511051986
    DMT mean: 0.925039860149637 median: 0.8775079611013612 var: 0.013972061992698738
    TCT mean: 0.8287505675975253 median: 0.8414537644132942 var: 0.07278953326828647
    DXT mean: 1.8831174517032294 median: 1.664530111592733 var: 0.8958620250203537
    CANDY mean: 0.6809140113214905 median: 0.7783641160949869 var: 0.08910712086650803
    CAS mean: 76.24064388614586 median: 0.8611581464912338 var: 13651.708818014826
    XID mean: 5.64731684434726 median: 0.9276679920874377 var: 227.55443792085188
    CLUB mean: 1.3521238617222409 median: 0.9936880612902743 var: 11.140800050700348
    NMS mean: 4.578192202865748 median: 0.7925793473401878 var: 131.36595861530725
    TMC mean: 0.9243110431461464 median: 0.9236641221374046 var: 0.057133978656562
    ACAT mean: 0.5824774457761028 median: 0.7268455061680046 var: 0.172299124643614
    B2X mean: 2499.8235187246305 median: 0.8819776714513557 var: 162353678.8097725
    SBC mean: 0.7896833418503795 median: 0.7189219751983468 var: 0.16784894778994197
    ESC mean: 75.4455048205163 median: 1.1266375545851528 var: 58917.61707247942
    EAG mean: 1.5831655902255881 median: 0.8658786301543158 var: 8.785551799165347
    SHND mean: 1.2782691128733992 median: 1.1666666666666667 var: 1.1990064847456612
    CPY mean: 204433.711220175 median: 204433.711220175 var: 41792833272.58724
    KZC mean: 4.774474042123886 median: 0.886104783599089 var: 132.5078349195041
    VASH mean: 1.0747340791905693 median: 0.9751676185746212 var: 0.2454219114517892
    SIC mean: 1.9978168467549569 median: 0.9733014624847348 var: 19.87205994647169
    PCS mean: 3.631861530085398 median: 0.9977700456834966 var: 560.3751180688193
    GEO mean: 1.1919970454507445 median: 0.9831932773109243 var: 2.1876361099649
    IFC mean: 1.2927014291160042 median: 0.8888888888888888 var: 4.314743380984515
    GCS mean: 34.34571933309708 median: 0.9162794976769861 var: 10283.123669377392
    TOK mean: 3.202171043054593 median: 1.0633187772925765 var: 63.21782562984637
    DRPU mean: 0.9281625440601526 median: 0.8601745429723741 var: 0.021236422898612713
    DIM mean: 0.7801894755473662 median: 0.7542097788598093 var: 0.07859168684680219
    GBG mean: 1.253205456038364 median: 1.0099046221570067 var: 1.3737024333470582
    IDXM mean: 8819.976245327878 median: 0.971241575946086 var: 559981355.806946
    MSD mean: 0.9374063652665777 median: 0.8678716547569006 var: 0.14750095141487568
    LDCN mean: 1.4181025735135924 median: 0.9775522282337699 var: 3.9953017041103016
    MVC mean: 1.629165562998662 median: 0.9748483023762103 var: 3.1881086706866495
    KB3 mean: 5.0073454384556975 median: 0.9443451909812522 var: 1170.4281323407297
    WC mean: 7.299328209887039 median: 0.9558823529411764 var: 766.4654111699826
    DTH mean: 0.4121050232341108 median: 0.13890228515503805 var: 0.17557515716720778
    GLA mean: 7.36600412338622 median: 10.307192879367314 var: 18.5410285727191
    LEPEN mean: 1.8205876158834355 median: 0.9596774193548386 var: 44.05766873495147
    SUP mean: 6.880957161130453 median: 0.9684174970444183 var: 75.29625087295177
    CEFS mean: 92130.73415805638 median: 0.8720693894355948 var: 84879068078.1786
    JEW mean: 0.5406333646846396 median: 0.6374529943312567 var: 0.11273275177876871
    XRY mean: 2.0476014514427545 median: 0.9776711562127031 var: 14.107128884939964
    OX mean: 5.080504803453503 median: 0.9227444944352358 var: 575.5909481968755
    TOKEN mean: 15.49109009100739 median: 1.0454545454545454 var: 10195.86734008251
    CSC mean: 11.222666239321784 median: 1.0150519137433187 var: 30847.35891022858
    THS mean: 3.3646765242421055 median: 1.0017281411566914 var: 386.6235422257089
    COR mean: 1.0452988916667207 median: 0.9847315629052822 var: 0.08399331892878587
    PRES mean: 1.3838722589737704 median: 0.9912854030501089 var: 9.05179296234216
    TRIA mean: 13.44570298722377 median: 1.0953947368421053 var: 2839.128817234584
    CLD mean: 0.8176613044539094 median: 0.8844212358572671 var: 0.18383948151565238
    BCA mean: 948.0179989479553 median: 0.7101857062464828 var: 7717747.490341198
    EDRC mean: 1.0595354893524425 median: 0.9582421330907644 var: 0.2955174850363131
    TER mean: 1162.4404823214531 median: 0.9152941176470588 var: 61208932.3435712
    SPK mean: 0.6274146238454373 median: 0.5968534906588004 var: 0.021056285517259635
    WA mean: 1.1441014933484064 median: 0.9820071797016588 var: 0.9767584243816141
    NAMO mean: 1.2261355621983567 median: 0.8673218673218672 var: 1.8153368705856152
    HC mean: 1713.4648486117258 median: 0.7238909909909909 var: 22879852.857298885
    BT2 mean: 80.4992689547487 median: 0.9538624947445288 var: 150348.51039374102
    ZBC mean: 1.6410897183840965 median: 0.9166733306677328 var: 43.080103241713566
    MCR mean: 3.935515388261075 median: 0.9203539823008849 var: 262.84696761348295
    DAV mean: 3.7073386505619053 median: 0.7263658391624377 var: 100.93988524381366
    SHA mean: 1.270418822889078 median: 0.7391304347826086 var: 13.5132149313125
    NOX mean: 25.538449925250113 median: 0.9022668116043203 var: 4377.43422023149
    CRAVE mean: 1.54636700877425 median: 1.3048973143759872 var: 12.987400555256563
    HTML5 mean: 3.4354829086290235 median: 1.0309278350515463 var: 615.1497682017283
    GRX mean: 631.1248507056443 median: 0.8379303917932576 var: 7866164.543328117
    TESLA mean: 1.2607182278031992 median: 0.9848484848484849 var: 3.2760001447255243
    GOD mean: 8.832782367018615 median: 0.8654647887323944 var: 545.032479148004
    SJW mean: 11.491692824469165 median: 1.3333333333333333 var: 3705.765865634421
    GOLF mean: 1.245730858434712 median: 1.1111111111111112 var: 2.3395030992404027
    RBBT mean: 1.3099566899359278 median: 1.4000000000000001 var: 0.8107512794459254
    CME mean: 1.438510005783352 median: 0.9836065573770492 var: 12.334945722881447
    ABC mean: 60.24201614831808 median: 0.9727195225916454 var: 218169.47626171345
    INDI mean: 0.7683832299734749 median: 0.5969096475260632 var: 0.38136842351627853
    PAYP mean: 1.0870072136658868 median: 1.0135135135135134 var: 0.2758930963964105
    BITCF mean: 15.909658741565313 median: 0.9579469391850248 var: 8748.17141521068
    UTT mean: 1.4550809642895226 median: 0.8826374374463056 var: 2.9124709836253846
    CYDER mean: 1.6463557048021895 median: 1.0734374999999998 var: 9.771441968757134
    DON mean: 1.1792012484135126 median: 0.8749999999999999 var: 7.047019896052069
    AV mean: 1.646815690223118 median: 1.02 var: 20.9077648072201
    INDIA mean: 1.1368323939969238 median: 0.9841772151898733 var: 0.9869006479466805
    DMC mean: 3.7989686181073483 median: 1.0000810065615315 var: 482.4567500925415
    GMX mean: 1.6643819979618495 median: 1.003144407037618 var: 7.552790102224413
    VULC mean: 1.5939941136992615 median: 0.9038594975224421 var: 8.120890709404966
    GARY mean: 1.3109456870467564 median: 1.005556336972637 var: 2.3331862619965453
    TELL mean: 2.7834012202318954 median: 1.1149425287356323 var: 106.83031187802189
    MINEX mean: 19.226220709366054 median: 1.055122637955307 var: 13190.820211948627
    BTCM mean: 1.6404352501026285 median: 0.8644452321871676 var: 6.361683109544492
    MARX mean: 1.129967380743439 median: 0.9469739952718677 var: 0.4646701589740113
    PLX mean: 3.4804061512121898 median: 0.936793516745784 var: 109.81651877037741
    FLAP mean: 1.8896416561619407 median: 0.8139534883720929 var: 184.8983664693536
    NEOG mean: 45.96747791067207 median: 0.9096385542168675 var: 42548.32816349747
    CMP mean: 68.4758276280914 median: 0.9817927170868348 var: 189837.7029493398
    XMRG mean: 0.7721066593940655 median: 0.8238636363636364 var: 0.15650740489600498
    UR mean: 1.419211938180369 median: 0.9183673469387755 var: 6.009254745668554
    SISA mean: 4.049868137327442 median: 0.9507004135362765 var: 187.18229027363597
    MUSE mean: 1.9190215971163138 median: 1.061742006615215 var: 135.2394196179821
    SMOKE mean: 1.176496666432429 median: 0.37354085603112835 var: 6.655184802307815
    XOT mean: 45.06842058005536 median: 1.0386568266304808 var: 120623.111962762
    ELITE mean: 1.1218874171197315 median: 0.9593493693902118 var: 0.6109793413526129
    SND mean: 1.3251509768233947 median: 0.9602543689320389 var: 1.2420291651713933
    SJCX mean: 1.1458995948332955 median: 0.9998268198349016 var: 1.0266298760947257
    TCOIN mean: 1.0944195646875896 median: 0.971830985915493 var: 0.48436360353797764
    GDC mean: 1.2757187838105253 median: 0.9629629629629629 var: 5.8181707030320515
    NTC mean: 167.26661083673758 median: 0.7797960784313726 var: 674010.8482789533
    NBIT mean: 1.1488641663273529 median: 1.0606427010184625 var: 0.6340315125073626
    GUESS mean: 2.4892092249020012 median: 0.46885428928558426 var: 23.53753626546569
    STEX mean: 1.2375958498762003 median: 0.9907333333333334 var: 1.2204537763772716
    FAZZ mean: 1.2021041245889725 median: 0.9321166473541908 var: 1.1116694598496553
    FRN mean: 1.4114495830063476 median: 0.9964576642762686 var: 4.737882875751554
    BIT mean: 1.3297997580897578 median: 0.9768467475192943 var: 2.068734741615726
    SAK mean: 1.1048173131460683 median: 0.9772997789491583 var: 0.6794031646859061
    JIYO mean: 1.8119059261958121 median: 1.9326732673267326 var: 1.9179613547065864
    SLOTH mean: 1.0757120591140898 median: 0.5652173913043479 var: 1.4313562156175461
    SIGMA mean: 59.920354330193625 median: 0.9439122739796011 var: 128364.3515997992
    SKR mean: 2.0001541102334217 median: 0.9862511457378551 var: 32.83256795791512
    BTE mean: 55.652458945982794 median: 0.8281430219146482 var: 59450.142105463434
    APC mean: 1.0828017873167837 median: 1.0044513457556934 var: 0.6546508590745026
    WOW mean: 1.1375832301400461 median: 0.9722114764667955 var: 1.5251790550624449
    NUMUS mean: 14.787730126525098 median: 0.7860199714693294 var: 1903.4438505458306
    ANTX mean: 1.0864183919774886 median: 1.0476190476190477 var: 0.2028126401818959
    XSTC mean: 1.4891570729689023 median: 1.0357142857142856 var: 7.425913036926812
    WINK mean: 1.1991928462972574 median: 1.0188356164383563 var: 0.5742863455675596
    KDC mean: 1.4053922567375832 median: 0.9141316904120138 var: 11.76763952091299
    FONZ mean: 1.6596033084760655 median: 1.8076923076923075 var: 0.5149979711724747
    ZENGOLD mean: 5.102896277250669 median: 0.9539909098158043 var: 856.3470703290271
    ACN mean: 1.5526118191015392 median: 0.9639489739323349 var: 50.34329114273311
    FID mean: 13.478574082939462 median: 1.0750045861614663 var: 5488.6145861976565
    HYPER mean: 1.1035710633921674 median: 1.0177738280382138 var: 0.40018615470667546
    TOPAZ mean: 1.595871271647705 median: 0.9534883720930232 var: 7.780843867046219
    UNRC mean: 1.0088688511375956 median: 0.9235880398671096 var: 0.31284943465206366
    TURBO mean: 1.0086914942993872 median: 1.0232558139534884 var: 0.11948080258237713
    GAY mean: 24.063715607221173 median: 0.9851913696884474 var: 21415.23714294997
    DUTCH mean: 1.03675866936869 median: 0.9683933274802459 var: 0.23315105626323548
    BITOK mean: 13209.509998527981 median: 0.9743589743589745 var: 8548746511.862647
    CFC mean: 3.428779582362261 median: 0.7419354838709677 var: 354.9426292138298
    XTD mean: 1.0547594518955052 median: 0.9405405405405406 var: 0.25586917324009373
    WSX mean: 1.1634133550334966 median: 1.1333333333333335 var: 1.462301745107903
    BSN mean: 1.1375151792769498 median: 1.0166288737717308 var: 0.4639596109018077
    LEVO mean: 2.8161743318935475 median: 1.196078431372549 var: 101.11880817546623
    DASHS mean: 1.2487856274879339 median: 0.9453109575518264 var: 0.9261021751843509
    HDLB mean: 1.3499638749389384 median: 0.9336186847444209 var: 2.3749358638517997
    GAIN mean: 1.6275427335614736 median: 1.0295857988165682 var: 19.53087455569724
    MCI mean: 2.113298182394491 median: 1.0088353811599948 var: 23.975402723965814
    HCC mean: 1.193600473264884 median: 0.9559822252033201 var: 1.1458079578177907
    ACES mean: 1.2784055034983324 median: 0.9783720930232558 var: 1.2396123615325028
    FFC mean: 1.0637982215800874 median: 0.9512761020881672 var: 0.45241833187204794
    ROYAL mean: 7.18282546835474 median: 0.9407925407925408 var: 3457.087787527807
    AKY mean: 29.434824715314136 median: 0.7138619591954855 var: 21704.893194745837
    REGA mean: 1.651998115667319 median: 0.850079744816587 var: 14.270595255470145
    SFE mean: 1.1976479118636432 median: 0.9175824175824175 var: 5.7970283190491445
    POKE mean: 1.2137841444644362 median: 1.0147058823529411 var: 1.9439780927548702
    LKC mean: 1.1983638954916715 median: 0.9865771812080537 var: 1.6756294364406574
    RYZ mean: 3.244040986485262 median: 0.9013525433695972 var: 88.04536915070736
    GRN mean: 1.3020659779894486 median: 0.9605522682445758 var: 4.273430470906948
    UNC mean: 1.1246721586063744 median: 0.970426184996445 var: 1.3548769794619848
    FAP mean: 26.203450327306026 median: 1.0288189381593618 var: 14776.191369547201
    PDG mean: 1.1950422510016643 median: 0.9885057471264368 var: 1.6085790349356448
    SHELL mean: 1.7875711841240747 median: 0.15277777777777776 var: 143.7568215547106
    ZSE mean: 1.5418479889471817 median: 0.9711368792538442 var: 9.40250989008039
    QORA mean: 60.58755501916617 median: 0.9519943650926201 var: 426671.1254857466
    DBG mean: 1.2302360509371661 median: 1.0446096654275094 var: 1.8614086639013323
    PRN mean: 1.358992940400009 median: 0.8999999999999999 var: 3.7132460368783122
    BTBc mean: 409.34846335229025 median: 0.901600474214582 var: 3869144.6927586794
    SKULL mean: 1.2057250048973351 median: 0.9889328198380785 var: 0.763386313768191
    BAC mean: 1.5189548203495082 median: 0.9730148883374689 var: 26.1588216351242
    HALLO mean: 1.0558514229911378 median: 1.0328638497652582 var: 0.15882726462921024
    XQN mean: 1.396740923218561 median: 0.9867403314917126 var: 22.382524078547352
    RUNNERS mean: 1.130819962450199 median: 1.0471491228070178 var: 0.397326891518208
    FUTC mean: 2.1442188858361924 median: 1.1185553358914682 var: 8.525562446037545
    TEAM mean: 1.0867990025040655 median: 1.0277777777777777 var: 0.24729099394781098
    VOYA mean: 6.287026180165606 median: 3.4593837535014007 var: 2814.9477782795857
    CC mean: 2.2786687507459 median: 0.923076923076923 var: 264.89568210874546
    RHFC mean: 3.174172976140164 median: 0.8966836734693878 var: 277.8323335778352
    RUBIT mean: 1.2902199306137248 median: 0.9624060150375939 var: 1.802861244753189
    MBL mean: 2.7945587000780128 median: 0.9753761969904241 var: 249.96816764982745
    BEST mean: 15.887438146247703 median: 0.9527983816587997 var: 14216.544509776282
    PRIMU mean: 1.0578102442225112 median: 0.953846153846154 var: 0.23660951244615236
    X2 mean: 1.077246819430163 median: 0.9504132231404958 var: 0.5193062793877287
    KARMA mean: 1.1317786400962813 median: 0.863013698630137 var: 0.8024108089396911
    MMXVI mean: 1.1575749624812732 median: 1.017857142857143 var: 0.5288538330930863
    PRM mean: 1.2801098025217785 median: 1.0499999999999998 var: 2.2607132333379374
    RICHX mean: 1.1827552773704424 median: 1.0501193317422435 var: 0.9106082470623429
    DCRE mean: 1.391766281599915 median: 0.9814585056520538 var: 5.267768084351176
    OPES mean: 1.2678420726190172 median: 1.0118343195266273 var: 1.5984782824282657
    AXIOM mean: 1.1283734816982227 median: 0.9547993019197208 var: 3.723695388317631
    SPORT mean: 1.0811138927747104 median: 0.9970484061393151 var: 0.29610675642454626
    TODAY mean: 1.1105960177156926 median: 1.0349959116925593 var: 0.3141099456176574
    ASN mean: 2.272986542389263 median: 0.8567639257294428 var: 22.79255800129072
    DUB mean: 1.1103839792417567 median: 1.0176470588235296 var: 0.3135522353099723
    HIGH mean: 1.880060572043292 median: 0.8408104196816207 var: 16.794948479383095
    OMC mean: 1.931901104321678 median: 1.0173191222306015 var: 66.26083237325794
    TRICK mean: 1.5430517382265652 median: 1.0239792611795202 var: 9.949443340455844
    XAU mean: 1.5465469969948638 median: 1.2013165112452 var: 1.218814647738177
    CYC mean: 1.0993267721334283 median: 0.9259259259259259 var: 0.9057053676522322
    TCR mean: 1.18050965356884 median: 0.9744897959183673 var: 0.7298722952721349
    YES mean: 18500.742117264013 median: 0.9819819819819819 var: 26405699385.501957
    IVZ mean: 2.008856565002422 median: 1.0379672927377477 var: 68.24193108810408
    PSY mean: 1.3897170414274425 median: 1.0220713073005092 var: 2.956160581521846
    MONETA mean: 1.1949590641514058 median: 1.0118694362017804 var: 1.5206476933707869
    XVE mean: 1.0897560883524668 median: 1.0172979797979798 var: 0.22767075851959817
    FRWC mean: 1.188011240435435 median: 1.0109414791672138 var: 1.255459889601457
    LAZ mean: 1.1902597515566165 median: 0.9867424242424244 var: 1.4973270475007308
    KASHH mean: 4.828655054298782 median: 0.9127819548872182 var: 1556.637041628406
    SNAKE mean: 31.457734212890216 median: 0.956942425542542 var: 54416.17928060285
    EGOLD mean: 1.1504875296188344 median: 0.995109895888106 var: 0.5042941951280983
    TOP mean: 7.95931178169337 median: 0.8809523809523809 var: 12908.414411060261
    GML mean: 1.263546475651317 median: 1.125 var: 7.75528723423784
    EGG mean: 2.622935020008863 median: 1.174309272385361 var: 115.2867439800505
    BUB mean: 2.5659132879206954 median: 1.9770151944372907 var: 53.22818839342376
    OP mean: 2.970046416362359 median: 1.0042075736325387 var: 469.12657774144185
    DISK mean: 1.1881082092350534 median: 0.9651162790697676 var: 0.9587500078016096
    LTH mean: 1.113339096841661 median: 1.0257260101010102 var: 0.35993189945033116
    MONEY mean: 1.4404875839776998 median: 1.0566037735849056 var: 4.223344762494704
    TLE mean: 5.0735031642977635 median: 0.9838831149269467 var: 270.5926793763363
    CHEAP mean: 1.274472265267395 median: 0.9921507064364209 var: 2.029010340223405
    BIRDS mean: 1.083683454207723 median: 1.0577367205542725 var: 0.2344821208042589
    LLT mean: 12.778410625899957 median: 0.9591180594829524 var: 5101.977297563133
    MAGN mean: 1.3674771134627384 median: 0.9292358651049311 var: 4.530555880817057
    OCOW mean: 1.1167177172539944 median: 1.0239043824701195 var: 0.6191250272395946
    
