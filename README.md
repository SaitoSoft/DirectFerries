# DirectFerriesTechTestSOA

This is a technical test soloution for a WebAPI. I didn't know if the soloution was SOA or Microservice so I just provided a simple SOA implenetation.

## Installation

No install needed just copy files to desired location. There are 3 tests (NUnit and Moq) that cover:

controller_action_should_return_a_ok_result

controller_action_should_return_a_bad_request_result_for_no_space_between_fullname_and_a_null_date

should_return_a_user_dto_object_with_values_for_specific_start_date (this is wrapped in a responseDTO object)

controller_action_should_return_a_user_object_with_values_for_specific_start_date

## Usage

Run Project and enter parameters in Swagger. These are:

Fullname (needs a space to denote fullname)

Dob ("yyyy-mm-dd" format)

TargetDate (this is used as an offset but if left blank a default date is provided to the service layer)

## Contributing

Since some of the code depends on a date (usually todays date). In order to get test passing with concrete values I have hard coded a date in the UserControllerTests (line 109 targetdate). 
This date is passed through to the service and used as an offset in the AgeExtensions calculations.

The offset days can be configured in appsettings for the task "A list that shows the 14 days before the user’s next birthday (days of week (Mon, Tue, Wed etc.)".
Currently it is set as 14 but can be changed to get a larger or smaller list of days before the next birthday.

Please make sure to update test setup data if the as appropriate if the offset days is changed.

I used Fine Code Coverage (xtn see attached documant CodeCoverage.docx for results). I wrapped the extention methods in function properties in the service so i could mock them in the tests for better code coverage.

Normally I would include a .gitignore file however since I am just adding code to a non dev/test/uat/sit/prod repo I have omitted this item.

## License

N/A
