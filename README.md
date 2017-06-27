Fortran Primes
=======

```Fortran
PROGRAM  Primes
   IMPLICIT  NONE
   
   INTEGER  :: Range, Number, Divisor, Count

   WRITE(*,*)  'What is the range ? '
   DO                                    
      READ(*,*)  Range                   
      IF (Range >= 2)  EXIT              
      WRITE(*,*)  'The range value must be >= 2.  Your input = ', Range
      WRITE(*,*)  'Please try again:'    
   END DO
   
   Count = 1                             
   WRITE(*,*)                            
   WRITE(*,*)  'Prime number #', Count, ': ', 2
   DO Number = 3, Range, 2               

      Divisor = 3                        
      DO
         IF (Divisor*Divisor > Number .OR. MOD(Number,Divisor) == 0)  EXIT
         Divisor = Divisor + 2           
      END DO

      IF (Divisor*Divisor > Number) THEN      
         Count = Count + 1               
         WRITE(*,*)  'Prime number #', Count, ': ', Number
      END IF
   END DO
   
   WRITE(*,*)
   WRITE(*,*)  'There are ', Count, ' primes in the range of 2 and ', Range
   
END PROGRAM  Primes
```

<p align="center">
	<img src="https://github.com/ginppian/Fortran.Primes/blob/master/img1.png" width="952" height="840">
</p>