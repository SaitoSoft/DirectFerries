# DirectFerriesTechTestSOA

This is a technical test soloution for a WebAPI. I didn't know if the soloution was SOA or Microservice so I just provided a simple SOA implenetation.

## Installation

No install neede just copy files to desired location

## Usage

Run Project and enter parameters in Swagger 

## Contributing

Since some of the code depends on a date (usually todays date). In order to get test passing with concrete values I have hard coded a date in the UserController 
tests (line 109 targetdate). This date is passed through to the service and used as an offset in the AgeExtensions calculations.

The offset days can be configured in appsettings for the task "A list that shows the 14 days before the user’s next birthday (days of week (Mon, Tue, Wed etc.)".
Currently it is set as 14 but can be changed to get a larger or smaller list of days before the next birthday.

Please make sure to update test setup data if the as appropriate if the offset days is changed.

## License

N/A
