# JSON-DB-WEB-PROJECT
### This ia simple web form project where the data are saved in the JsonPowerDB data base.

- Benifits of ysing Json PowerDB
    - Minimum Development Cost<br/>
    - Minimum Time to Market.<br/>
    - Minimize the complexity of interoperability of different applications.<br/>
    - Maximum data processing performance.<br/>
    - Technology Futuristic.<br/>
    - Fills gap from database to big-data.<br/>
    - Pluggable with new algorithms. Pluggable and user defined API.<br/>
    - Minimize Total Cost of Ownership.<br/>
    
### Release History:
    
```
<script>
$('#empId').focus()
function validateAndGetFormData() {
  var empIdVar = $('#empId').val()
  if (empIdVar === '') {
    alert('Employee ID Required Value')
    $('#empId').focus()
    return ''
  }
  var empNameVar = $('#empName').val()
  if (empNameVar === '') {
    alert('Employee Name is Required Value')
    $('#empName').focus()
    return ''
  }
  var empEmailVar = $('#empEmail').val()
  if (empEmailVar === '') {
    alert('Employee Email is Required Value')
    $('#empEmail').focus()
    return ''
  }
  var jsonStrObj = {
    empId: empIdVar,
    empName: empNameVar,
    empEmail: empEmailVar,
  }
  return JSON.stringify(jsonStrObj)
}
function resetForm() {
  $('#empId').val('')
  $('#empName').val('')
  $('#empEmail').val('')
  $('#empId').focus()
}
function saveEmployee() {
  var jsonStr = validateAndGetFormData()
  if (jsonStr === '') {
    return
  }
  var putReqStr = createPUTRequest(
    '90936861|-31948784479254024|90932362',
    jsonStr,
    'SAMPLE',
    'EMP-REL',
  )
  alert(putReqStr)
  jQuery.ajaxSetup({ async: false })
  var resultObj = executeCommandAtGivenBaseUrl()(
    putReqStr,
    'http://api.login2explore.com:5577',
    '/api/iml',
  )
  alert(JSON.stringify(resultObj))
  jQuery.ajaxSetup({ async: true })
  resetForm()
}
</script>        
```
#### Javascript library was used to make it easy for the developers to work with Json PowerDB

```
<script src=" http://login2explore.com/jpdb/resources/js/0.0.3/jpdb-commons.js "></script>
```
