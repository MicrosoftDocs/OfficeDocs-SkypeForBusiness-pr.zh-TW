---
title: 商務用 Skype Server 2015 中的會議表格
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: c3da6271-b3c6-4898-894f-10456ec794d0
description: 此表格中的每一筆記錄都包含有關一部會議的呼叫詳細資料。
---

# <a name="conferences-table-in-skype-for-business-server-2015"></a>商務用 Skype Server 2015 中的會議表格
 
此表格中的每一筆記錄都包含有關一部會議的呼叫詳細資料。
  
|**欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |主要  <br/> |CDR 代理程式捕獲會議要求的時間。 僅用作主鍵，以唯一識別會議實例。  <br/> |
|**SessionIdSeq** <br/> |int  <br/> |主要  <br/> |識別工作階段的 ID 號碼。 與 **SessionIdTime** 搭配使用，以唯一識別會議實例。 * <br/> |
|**ConferenceUriId** <br/> |int  <br/> |Foreign  <br/> |會議 URI。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中的 ConferenceUris 表格](conferenceuris.md)。 <br/> |
|**ConfInstance** <br/> |唯一  <br/> | <br/> |適用于週期性會議;每個週期性會議實例都具有相同的 **ConferenceUri**，但會有不同的 **ConfInstance**。 <br/> |
|**ConferenceStartTime** <br/> |datetime  <br/> | <br/> |會議開始時間。  <br/> |
|**ConferenceEndTime** <br/> |datetime  <br/> | <br/> |會議開始時間。  <br/> |
|**PoolId** <br/> |int  <br/> |Foreign  <br/> |識別碼，用來識別捕獲會議的集區。 如需詳細資訊，請參閱 [pool 表格](pools.md) 。 <br/> |
|**OrganizerId** <br/> |臨界值  <br/> |Foreign  <br/> |識別此會議之召集人 URI 的識別碼號碼。 如需詳細資訊，請參閱 [Users 表格](users.md) 。 <br/> |
|**Flag** <br/> |Smallint  <br/> || 包含會議屬性的位元遮罩。 可能的值為： <br/>  0X01 <br/>  合成 <br/>  交易 <br/> |
|**處理** <br/> |位  <br/> ||監控服務所使用的內部欄位。  <br/> 此欄位是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||供監控服務內部使用。  <br/> 此欄位是在商務用 Skype Server 2015 中引入。  <br/> |
   
\* 對於大部分的會話，SessionIdSeq 的值會是1。 如果兩個會話的開始時間完全相同，則 SessionIdSeq 為1，而另一個會是2，依此類推。
  

