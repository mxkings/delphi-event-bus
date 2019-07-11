![alt text](/docs/DEB_Logo.png "DEB Logo")

# DEB an Event Bus framework for Delphi
Delphi Event Bus (for short DEB) is a publish/subscribe Event Bus framework for the Delphi platform.

DEB is designed to decouple different parts/layers of your application while still allowing them to communicate efficiently.
It was inspired by EventBus framework for the Android platform.

![alt text](/docs/DelphiEventBusArchitecture.png "Delphi Event Bus Architecture")

## Features
* __Easy and clean:__ DelphiEventBus is super easy to learn and use because it respects KISS and "Convention over configuration" design principles. By using default TEventBus instance, you can start immediately to delivery and receive events 
* __Designed to decouple different parts/layers of your application__
* __Event Driven__
* __Attributes based API:__ Simply put the Subscribe attribute on your subscriber method you are able to receive a specific event
* __Support different delivery mode:__ Specifying the TThreadMode in Subscribe attribute, you can choose to delivery the event in the Main Thread or in a Background ones, regardless where an event was posted. The EventBus will manage Thread synchronization     
* __Unit Tested__
* __Thread Safe__

## Show me the code
1.Define events:

```delphi
TEvent = class(TObject)
// additional information here
end;
```

2.Prepare subscribers:

 * Declare your subscribing method:
```delphi
[Subscribe]
procedure OnEvent(AEvent: TAnyTypeOfEvent);
begin
  // manage the event 	
end;
```

 * Register your subscriber:
```delphi
TEventBus.GetDefault.RegisterSubscriber(self);
```

3.Post events:
```delphi
  TEventBus.GetDefault.post(LEvent);
```

##Support
* DEB is a 100% ObjectPascal framework so it works on VCL and Firemonkey
* It works with Delphi2010 and major

## License
  Copyright 2016-2019 Daniele Spinetti

  Licensed under the Apache License, Version 2.0 (the "License");
  you may not use this file except in compliance with the License.
  You may obtain a copy of the License at

  http://www.apache.org/licenses/LICENSE-2.0

  Unless required by applicable law or agreed to in writing, software
  distributed under the License is distributed on an "AS IS" BASIS,
  WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
  See the License for the specific language governing permissions and
  limitations under the License.
