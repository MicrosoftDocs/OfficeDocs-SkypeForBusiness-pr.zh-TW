---
title: 媒體視圖
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 1a7b2e59-082e-4188-98ae-48ae9bd3494a
description: 媒體檢視可儲存對等工作階段中所使用之一種媒體類型的相關資訊。 若某階段工作使用了一種以上的媒體類型，則在表格中會呈現多個記錄。 此視圖已引進于 Microsoft Lync Server 2013。
ms.openlocfilehash: 9e1165e19db4d007f04007233a7751a9119fcf310cf61b257e7e5014599357c2
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54322955"
---
# <a name="media-view"></a>媒體視圖
 
媒體檢視可儲存對等工作階段中所使用之一種媒體類型的相關資訊。 若某階段工作使用了一種以上的媒體類型，則在表格中會呈現多個記錄。 此視圖已引進于 Microsoft Lync Server 2013。
  
> [!NOTE]
> 您不應使用媒體檢視來計算工作階段的媒體持續期間。此檢視包含工作階段中的媒體交換訊號詳細資料。媒體交換是由 INVITE 要求來執行，且 StartTime 會指出 INVITE 傳送出來的時間。邀請時間不一定表示媒體開始時間，因為只有在接受工作階段後，媒體才會開始。 
  
除了下列所列之外，媒體視圖還會包含 [SessionDetails 視圖](sessiondetails-0.md) 中的所有欄。
  
|**欄**|**資料類型**|**詳細資料**|
|:-----|:-----|:-----|
|**媒體** <br/> |Nvarchar (256)   <br/> |媒體類型。 如需詳細資訊，請參閱 [MediaList 表格](medialist.md) 。 <br/> |
|**MediaStartTime** <br/> |datetime  <br/> |媒體要求傳送出來的時間。  <br/> |
|**MediaEndTime** <br/> |datetime  <br/> |工作階段結束時間。  <br/> |
   

