---
title: Lync Server 2013：大型會議排程處理常式
description: Lync Server 2013：大型會議排程處理常式。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Large-meeting scheduling process
ms:assetid: de267458-885f-4176-a8d7-1a218e67640e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205334(v=OCS.15)
ms:contentKeyID: 48185639
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 96d383b6da96fb7d36e031485feac2ff927df347
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557589"
---
# <a name="large-meeting-scheduling-process-in-lync-server-2013"></a>Lync Server 2013 中的大型會議排程處理常式

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-22_

因為在專屬的大型會議集區上一次只支援一個大型會議，所以建議您執行大型會議排程程式，以協助避免大型會議衝突。 這類排程處理的目的是為了協助設定大型會議。 Lync Server 或 Lync Server 用戶端不會直接提供這類功能。 實施這類程式的其中一個方法是使用貴組織的支援小組的票證系統（如果有的話）。

對於大型會議的召集人，排程大型會議需要完成下列步驟：

1.  會議召集人或代理人會決定即將召開之會議的時間、工期和大小，以及簡報者清單。 如果預期的會議大小超過250的使用者，或是為了確保會議的使用者體驗低於250的使用者，召集人或代理人會送出大型會議的要求。

2.  排程員工會檢查是否有可用的要求日期和時間。 因為我們一次只支援專屬集區的單一大型會議，所以排程人員需要檢查大型會議行事曆，以判斷是否有針對要求的日期和時間排定的其他會議。 如果有可用的要求時間，則人員會核准會議邀請。

3.  如果已核准要求，排程員工 (使用專用集區上的認證) 使用 Lync 2013 的線上會議增益集，以供 Outlook 在專屬的大型會議集區上設定會議。 加入會議時所使用的 URL 會提供給申請者，做為核准通知的一部分。

4.  會議召集人或代理人會使用 Outlook 來排程即將召開的會議，新增將會議加入會議邀請的 URL。 會議召集人或代理人會指定要邀請的使用者，併發出會議邀請。
    
    下圖說明排定大型會議的一般要求與核准工作流程。
    
    ![5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d](images/JJ205334.5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d(OCS.15).jpg "5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d")  

</div>

<span> </span>

</div>

</div>

</div>

