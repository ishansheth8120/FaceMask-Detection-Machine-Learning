# Realtime FaceMask Detector

Given the circumstances, wearing a mask is crucial. There are numerous enclosed spaces where entrance without a mask is prohibitted, and officials are stationed to limit those without mask for a variety of reasons. The identification of masks is automated by this machine learning-based algorithm. This method automates the task of recognizing faces with or without a facemask, greatly reducing manual labor.

## Objective 
To develop a system that can determine whether or not a person is wearing a face mask
- Automating Mask Detection

## Primary tasks 
                1. Load images using openCV in Python
                2. Convert images into array with RGB values
                3. After loading, perform Violas Jones Face Detection Algorithm


The project makes use of a Image Processing using OpenCV
## OpenCV - 
          1. Open Source Computer Vision and Machine Learning Softeare Library. It  has more than 2500 optimized algorithm.  
          2. The main task of openCV is loading images in Python and converting those into arrays
          3. Each index of array represents(red, green, blue) color pixels which ranged from 0-255
          
## Object Detection algorithm used             
Violas Jones algorithm has 4 stagees - 1. Haar Feature
                                       2. Creating integral image
                                       3. Adaboost Training
                                       4. cascading classifier 
 
The Haar frontal face algorithm is used in this project. On every human face, there are certain common traits with darker and brighter regions.
Haar recognises these areas and recognises the face. If the difference between summation of pixels in bright area and that of dark area is closed to 1 there exists a Human face.


# Conclusion
1. The models were evaluated using images and real time video feeds using machine learning
2. This may be further improved with the help of Deep Learning and by automating the process of feature selection with feeding a lot more data and tuning hyperparameters.

<img width="911" alt="image" src="https://user-images.githubusercontent.com/71434443/176613542-06128ab4-2405-4f2e-bbdb-7b28864cff04.png">

@Test
public void testBeginProcess() throws Exception {
    // mock dependencies
    SolaHelper solaHelper = mock(SolaHelper.class);
    FxRateHelper fxRateHelper = mock(FxRateHelper.class);
    ExceptionHandler exceptionHandler = mock(ExceptionHandler.class);

    // create test data
    List<Integer> rateSetIds = Arrays.asList(1, 2, 3);
    String solaFxRateDate = "2022-02-01";

    // create test instance
    MyClass myClass = new MyClass(solaHelper, fxRateHelper, exceptionHandler);

    // mock solaHelper.fetchFXRate() to return test data
    FxRateDataResponse fxRateDataResponse = new FxRateDataResponse();
    Meta meta = new Meta();
    meta.setTotalCount(3);
    fxRateDataResponse.setMeta(meta);
    Result result = new Result();
    List<Result> resultList = new ArrayList<>();
    resultList.add(result);
    fxRateDataResponse.setResult(resultList);
    when(solaHelper.fetchFXRate(eq(1), any(LocalDate.class))).thenReturn(fxRateDataResponse);
    when(solaHelper.fetchFXRate(eq(2), any(LocalDate.class))).thenReturn(fxRateDataResponse);
    when(solaHelper.fetchFXRate(eq(3), any(LocalDate.class))).thenReturn(fxRateDataResponse);

    // call the method
    myClass.beginProcess(rateSetIds, solaFxRateDate);

    // verify that the necessary methods were called
    verify(solaHelper, times(3)).fetchFXRate(anyInt(), any(LocalDate.class));
    verify(fxRateHelper, times(3)).processFxRateData(anyList(), any(Meta.class));
    verify(exceptionHandler, times(1)).generateAlerts();
}

