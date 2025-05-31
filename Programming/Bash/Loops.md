### For

```bash
for variable in 1 2 3 4
do
	echo $variable
done
```

### While

```bash
#!/bin/bash

counter=0

while [ $counter -lt 10 ]
do
  # Increase $counter by 1
  ((counter++))
  echo "Counter: $counter"

  if [ $counter == 2 ]
  then
    continue
  elif [ $counter == 4 ]
  then
    break
  fi
done
```

```shell-session
./WhileBreaker.sh

Counter: 1
Counter: 2
Counter: 3
Counter: 4
```

### Until

El código dentro de un untilel bucle se ejecuta siempre y cuando la condición particular sea false.

```bash
#!/bin/bash

counter=0

until [ $counter -eq 10 ]
do
  # Increase $counter by 1
  ((counter++))
  echo "Counter: $counter"
done
```

```shell-session
./Until.sh

Counter: 1
Counter: 2
Counter: 3
Counter: 4
Counter: 5
Counter: 6
Counter: 7
Counter: 8
Counter: 9
Counter: 10
```
