---
title: Lync Server 2013： 設定圖庫檢視
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Gallery View
ms:assetid: 4a609178-47d8-4682-ac8d-29f882801924
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204871(v=OCS.15)
ms:contentKeyID: 48184069
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 02c13f2b1fa312394edfaba01ecd05179f86a0c9
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151423"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-gallery-view-in-lync-server-2013"></a>在 Lync Server 2013 中設定圖庫檢視

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-30_

在 Lync Server 2013 中，您可以設定圖庫檢視 」 視訊會議的會議原則。 「圖庫檢視」預設為開啟狀態。 如果您不想允許「圖庫檢視」，或只想針對部分使用者允許「圖庫檢視」，必須在會議原則中關閉此功能。

會議參與者的視訊無法使用時，如果您將部署高解析度相片，Lync Server 2013 中的新功能，可以被增強使用者的圖庫檢視經驗。 高解析度相片提供較小，有限的解析度連絡人相片儲存在 Active Directory 網域服務中的替代方案。 高解析度相片儲存在使用者的 Exchange 2013 信箱，且，因此，需要您整合 Lync Server 2013 和 Exchange 2013。 如需詳細資訊，請參閱 NextHop 部落格文章，「 整合 Exchange 2013 和 Lync Server 2013 中，「 [https://go.microsoft.com/fwlink/p/?LinkId=260987](https://go.microsoft.com/fwlink/p/?linkid=260987)。

<div>


> [!NOTE]  
> 每個網誌的內容及其 URL 如有變更，恕不另行通知。



</div>

您可以檢視或修改圖庫檢視 」 參數，藉由使用 Lync Server 2013 控制台，或使用下列其中一個下列 cmdlet:

  - **Get-csconferencingpolicy**

  - **Set-csmonitoringserver**

  - **New-csconferencingpolicy**

請使用下列會議原則設定來設定「圖庫檢視」：

  - **AllowMultiview**   此參數會控制是否允許使用者組織圖庫檢視視訊會議。 此參數適用於排程會議及使用者建立的臨時會議。
    
    範例:
    
      - 此參數設為 True 的使用者 A，隸屬於 Lync Server 2013 集區中。 由使用者 A 召集的會議可讓使用者加入及接收多個視訊資料流。
    
      - 此參數設為 False，使用者 b，隸屬於 Lync Server 2013 集區。 依使用者 B 的會議有單一的視訊資料流，類似於 Lync Server 2010 所提供的視訊會議經驗。
    
    此參數決定誰可以召集允許多個視訊資料流的會議。允許多個視訊資料流的會議的參與者是否可以接收多個視訊資料流，要視他們的個人權限而定 (請參閱 EnableMultiviewJoin 參數描述)。

  - **EnableMultiviewJoin**   此參數會控制會議的參與者是否在會議中允許其接收圖庫檢視視訊體驗。 此參數控制使用者在所有參與的會議中的體驗。
    
    範例:
    
      - 此參數設為 True，針對 C 使用者 C.使用者可以接收多個視訊資料流生於參與會議主辦或由使用者 A C 使用者啟動單一的視訊資料流，類似於 Lync Server 2010 所提供的視訊會議經驗時參與會議主辦或啟動使用者 b。
    
      - 此參數設為 False 的使用者 d 使用者 D 收到單一視訊資料流，類似於參與任何會議組織時，Lync Server 2010 所提供的視訊會議經驗的使用者或使用者 b。

下列程序是使用 Lync Server 管理命令介面來啟用圖庫檢視 」 視訊會議的範例。

<div>

## <a name="to-modify-conferencing-policy-for-gallery-view-video-conferencing"></a>修改「圖庫檢視」視訊會議的會議原則

1.  啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。

2.  在命令列上執行下列 Cmdlet 以編輯會議原則：
    
        Set-CsConferencingPolicy -Identity Pool01ConferencingPolicy -AllowMultiview $true -EnableMultiviewJoin $true 

</div>

</div>

<span> </span>

</div>

</div>

</div>

