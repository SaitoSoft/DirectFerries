# DirectFerriesTechTestSOA

This is a technical test soloution for a WebAPI. I didn't know if the soloution was SOA or Microservice so I just provided a simple SOA implenetation.

## Installation

No install needed just copy files to desired location. There are 3 tests (NUnit and Moq) that cover:

should_return_a_ok_result

should_return_a_bad_request_result_for_no_space_between_fullname_and_a_null_date

should_return_a_user_dto_object_with_values_for_specific_start_date (this is wrapped in a responseDTO object)

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

I used Fine Code Coverage (xtn) and the service code are not covered. However since the service only consists of one public and one private method I thought added additional tests for the service would be redundant since the the Controller test gets the data from the service.

## License

N/A
