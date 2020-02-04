---
title: Lync Server 2013：大型會議排程處理常式
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
ms.openlocfilehash: b2cfe26b70db612249ca840c86b41fb3d60db663
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738213"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="large-meeting-scheduling-process-in-lync-server-2013"></a>Lync Server 2013 中的大型會議排程流程

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-22_

因為在專門大型的會議池中只支援一支大型會議，我們建議您實施大型會議排程程式來協助避免大型會議的衝突。 此排程程式的目的是協助您設定大型會議。 Lync Server 或 Lync Server 用戶端不會直接提供此類功能。 實施這類程式的其中一個方法是使用貴組織的支援小組的票證系統（如果有的話）。

針對大型會議召集人，排程大型會議需要完成下列步驟：

1.  除了簡報者清單之外，會議召集人或代理人決定近期會議的時間、持續時間及大小。 如果預期的會議大小超過250的使用者，或可確保會議的使用者經驗少於250個使用者，召集人或代理人會提交大型會議的要求。

2.  排程員工會檢查是否有可用的要求日期和時間。 因為我們一次只支援專用池的單一大型會議，所以排程員工必須檢查大型會議行事曆，以判斷是否有針對要求的日期和時間排程其他會議。 如果有所要求的時間，員工會核准會議邀請。

3.  如果要求受到核准，排程員工（在專用的池中使用認證）會使用 Lync 2013 的線上會議增益集，在專用大型會議池子上設定會議。 要用來加入會議的 URL 會提供給申請者，作為核准通知的一部分。

4.  會議召集人或代理人會使用 Outlook 來排程即將到來的會議，新增加入會議的 URL 至會議邀請。 [會議召集人] 或 [代理人] 會指定受邀的使用者，併發出會議邀請。
    
    下圖說明用於排程大型會議的一般要求與核准工作流程。
    
    ![5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d](images/JJ205334.5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d(OCS.15).jpg "5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d")  

</div>

<span> </span>

</div>

</div>

</div>

