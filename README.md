# TTLock-php-sdk
php sdk for TTLock

## Install
```bash
composer require mannfai/ttlock
```

## 使用
```php
use mannfai\ttlock;
...

$ttlock = new TTLock($clientId,$clientSecret);
// oauth2
$ttlock->oauth2->token($username,$password,$redirect_uri);
$ttlock->oauth2->refreshToken($refresh_token,$redirect_uri);

// date is  Current time (in millisecond)
$ttlock->user->register($username,$password,$date);
// Reset password
$ttlock->user->resetPassword($username,$password,$date);

$ttlock->user->list($startDate,$endDate,$pageNo,$pageSize,$date);
$ttlock->user->delete($username,$date);

// Lock
$ttlock->lock->initialize($lockData,$date,$lockAlias);
$ttlock->lock->list($pageNo,$pageSize,$date);
$ttlock->lock->listKey($lockId,$pageSize,$date);
$ttlock->lock->deleteAllKey($lockId,$date);
$ttlock->lock->listKeyboardPwd($lockId,$pageNo,$pageSize,$date);
$ttlock->lock->changeAdminKeyboardPwd($lockId,$password,$date);
$ttlock->lock->changeDeletePwd($lockId,$password,$date);
$ttlock->lock->rename($lockId,$lockAlias,$date);
$ttlock->lock->resetKey($lockId,$date);
$ttlock->lock->resetKeyboardPwd($lockId,$pwdInfo,$timestamp,$date);
$ttlock->lock->getKeyboardPwdVersion($lockId,$date);
$ttlock->lock->updateElectricQuantity($lockId,$electricQuantity,$date);
$ttlock->lock->transfer($receiverUsername,$lockIdList,$date);


// Passcode
$ttlock->passcode->get( int $lockId, int $keyboardPwdVersion, int $keyboardPwdType, int $startDate, int $endDate, int $date ) : array
$ttlock->passcode->delete( int $lockId, int $keyboardPwdId, int $deleteType, int $date ):array
$ttlock->passcode->change( int $lockId, int $keyboardPwdId, string $newKeyboardPwd, int $startDate, int $endDate, int $changeType, int $date ) : array
$ttlock->passcode->add( int $lockId, string $keyboardPwd, int $startDate, int $endDate, int $addType, int $date ) : array



// 其他接口本次开发没用上 后续有需要再完善

    
```
## TODO
- Result Model
