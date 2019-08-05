---
title: 媒體視圖
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1a7b2e59-082e-4188-98ae-48ae9bd3494a
description: 媒體視圖儲存點對點工作階段中所使用之一個媒體類型的相關資訊。 如果使用一個以上的媒體類型, 則資料表中的多筆記錄會代表一個會話。 此視圖已在 Microsoft Lync Server 2013 中推出。
ms.openlocfilehash: 044a31381d4e1e48c465f7ee6de89acab10ab54e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192826"
---
# <a name="media-view"></a>媒體視圖
 
媒體視圖儲存點對點工作階段中所使用之一個媒體類型的相關資訊。 如果使用一個以上的媒體類型, 則資料表中的多筆記錄會代表一個會話。 此視圖已在 Microsoft Lync Server 2013 中推出。
  
> [!NOTE]
> 媒體視圖不應該用來計算會話的媒體持續時間。 此視圖包含會話中媒體交換的信號詳細資料。 媒體交換是由邀請要求所完成, 而 StartTime 則會指出邀請的傳送時間。邀請時間不一定代表媒體開始時間, 因為媒體只有在接受會話之後才會啟動。 
  
媒體視圖會包含 [ [SessionDetails] 視圖](sessiondetails-0.md)中的所有資料行, 以及以下所列的欄。
  
|**左欄**|**資料類型**|**詳細資料**|
|:-----|:-----|:-----|
|**媒體** <br/> |Nvarchar (256)  <br/> |媒體類型。 如需詳細資訊, 請參閱[MediaList 資料表](medialist.md)。 <br/> |
|**MediaStartTime** <br/> |datetime  <br/> |媒體要求的傳送時間。  <br/> |
|**MediaEndTime** <br/> |datetime  <br/> |會話的結束時間。  <br/> |
   

