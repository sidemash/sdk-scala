# sdk-scala
Sdk for live video streaming with Sidemash Cloud in Scala 

## Installation

## Configuration
First create an `AuthAccess` object to query Sidemash Cloud with API. On creation, you will have a token and a privateKey : Use them to initialize a client.
```scala 
import com.sidemash.SidemashClient
import com.sidemash.Credentials

val sdm = SidemashClient(Credentials(token = "1234", privateKey ="secret"))
```

## Usage 
### Get ressources
```scala
sdm.streamSquare.get(id = "1234")
```

### List resources
```scala 
sdm.streamSquare.list(where = Some("createdTime:in:[Yesterday.14h, Yesterday.15h["))
```
```scala 
import com.sidemash.form.ListStreamSquareForm
sdm.streamSquare.list(form = ListStreamSquareForm(orderBy = Some("createdTime:ASC,status:DESC")))
```

### Create resources
```scala
sdm.streamSquare.create(size = StreamSquare.Size.S,isElastic = false)
```
```scala
import com.sidemash.model.StreamSquare
import com.sidemash.form.CreateStreamSquareForm

sdm.streamSquare.create(form = CreateStreamSquareForm(size = StreamSquare.Size.S, isElastic = false))
```

### Update resources
```scala 
sdm.streamSquare.update(id = "1234", newSize = Some(StreamSquare.Size.S))
```
```scala 
import com.sidemash.form.UpdateStreamSquareForm

sdm.streamSquare.update(form = UpdateStreamSquareForm(id = "1234", newSize = Some(StreamSquare.Size.S)))
```

### Delete resources 
```scala
sdm.streamSquare.delete(id = "1234")
```


