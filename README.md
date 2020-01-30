# ApplitoolsTestResultsHandler - Python
### v2.0.1

The Applitools Test Results Handler extends the capabilities of TestResults with additional API calls.
With these additional API calls you will be able to retrive additional details at the end of the test.

Note: The Test Results Handler requires your account View Key - which can be found in the admin panel. Contact Applitools support at support@applitools.com if you need further assistance retrieving it.

## The images that can be downloaded are:

- The test baseline image - Unless specified, the images will be downloaded to the working directory.

- The actual images - Unless specified, the images will be downloaded to the working directory.

- The images with the differences highlighted - Unless specified, the images will be downloaded to the working directory.

- Get the status of each step [Missing, Unresolved, Passed, New]

### How to use the tool:

##### To initialize the Handler:
```python
test_results = eyes.close(False)
test_results_handler = ApplitoolsTestResultsHandler.ApplitoolsTestResultsHandler(test_results, "ViewKey")
```

##### **download_diffs** -  Downloading the test images with the highlighted detected differences to a given directory. In case of New, Missing or passed step no image will be downloaded.
```python
test_results_handler.download_diffs(Path_to_directory)
```

##### **download_images** -  Downloading the test baseline image and current image to a given directory.
```python
test_result_handler.download_images(Path=Path_to_directory) 
```

##### In addition to downloading the images of the test, the TestResultsHandler also gives access through code to the visually comparison result per step. It returns an array of elements called RESULT_STATUS which can be one of the following four options: PASS, UNRESOLVED, NEW or MISSING
```python
steps_results_array = test_result_handler.calculate_step_results()
```

# Further regarding:

Getting Diff Images Manually - http://support.applitools.com/customer/portal/articles/2457891 
Getting Current/Baseline Images Manually - http://support.applitools.com/customer/portal/articles/2917372
Extend API features with EyesUtilities - http://support.applitools.com/customer/portal/articles/2913152