---
title: Lync Server 2013： 大型會議排程處理序
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
ms.openlocfilehash: a11e24f6131ace7323a407d739e2174b24b57a7e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42186746"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="large-meeting-scheduling-process-in-lync-server-2013"></a>Lync Server 2013 中的大型會議排程處理序

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-22_

因為一次只能執行一個大型會議支援的專用的大型會議集區上，我們建議您實作大型會議排程處理程序，協助防範大型會議衝突。 這類排程程序的目的是協助大型會議的設定。 這類功能不是提供直接 Lync Server 或 Lync Server 用戶端。 實作這類程序的一種方式是使用您的組織支援小組的票證系統中，如果有的話。

大型會議的召集人，排程大型會議需要完成下列步驟：

1.  會議召集人或委派來決定時間、 期間和即將來臨的會議，除了的簡報者清單的大小。 如果預期的會議大小超過 250 位使用者，或若要確保少於 250 位使用者的會議的最佳使用者經驗，召集人或委派送出大型會議要求。

2.  排程的人員會檢查是否有可用的要求的日期和時間。 由於我們支援只有單一大型會議的專屬集區上一次，排程人員需要檢查大型會議行事曆，以判斷是否有另一個會議排程要求的日期和時間。 如果使用要求的時間，則人員核准會議邀請。

3.  如果核准要求，（使用專用的集區上的認證） 排程工作人員使用線上會議增益集與 Outlook 的 Lync 2013 的設定專用的大型會議集區上的會議。 要用來加入會議的 URL 提供給要求者的核准明的一部分。

4.  會議召集人或委派使用 Outlook 來排定即將來臨的會議，新增至會議邀請中加入會議的 URL。 會議召集人或委派，會指定使用者的邀請，並送出的會議邀請。
    
    下圖說明的一般要求與核准工作流程排程大型會議。
    
    ![5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d](images/JJ205334.5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d(OCS.15).jpg "5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d")  

</div>

<span> </span>

</div>

</div>

</div>

