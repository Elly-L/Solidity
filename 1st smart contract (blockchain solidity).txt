// SPDX-License-Identifier: GPL-3.0
pragma solidity >=0.7.0 <0.9.0;
//contract name
contract  SimpleStorage {

     uint256  favouriteNumber ;
//structures
     struct People {

         uint256 favouriteNumber;
         string name;   
     }
     //arrays
     People[] public people;
     //mapping
     mapping (string => uint256) public nameToFavouriteNumber;
     mapping ( uint256 => string) public FavouriteNumberToname;

     People public person = People({favouriteNumber: 2, name: "Log"});

      function store ( uint256 _favouriteNumber) public {
          favouriteNumber = _favouriteNumber;
      }

      function retrieve () public view returns(uint256) {
          return favouriteNumber; 
      }

      // memory is used for temporary while storage is used for permanent 

      function addPerson(string memory _name, uint256 _favouriteNumber ) public 
      {people.push(People(_favouriteNumber, _name));
      nameToFavouriteNumber[_name] = _favouriteNumber;
      FavouriteNumberToname[_favouriteNumber]= _name;
      }
      
}