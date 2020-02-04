---
title: Lync Server 2013：會議的排程詳細資料
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scheduling details
ms:assetid: 39ca6fff-2c15-4347-9f1f-6c8687a39a49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204823(v=OCS.15)
ms:contentKeyID: 48183910
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a4a0f85e93588e725e825fee22a8c2e95b74095b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764951"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scheduling-details-for-meetings-in-lync-server-2013"></a>Lync Server 2013 中的會議排程詳細資料

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-04_

在您檢查並確定未在要求的時間前排程任何其他會議之後，處理要求的大型會議支援人員會在大型會議泳池上排程會議。 使用與 Lync Server 2013 用戶端一起安裝的 Lync 線上會議增益集，在專用大型會議池中使用 Lync Server 啟用的使用者認證來執行這項工作。

若要確保最佳的使用者體驗，請務必按照適合會議召集人需求的正確存取層級和會議設定來排程大型會議。 我們建議在 Lync 會議選項中設定下列排程設定：

  - 針對每個大型會議使用新的會議空間，而不是重複使用專用會議空間。

  - 指定會議存取層級，如下所示：
    
      - 如果組織中至少有一個受邀者，請將會議存取類型設定為 **[任何人] （無限制**）。 這可讓您避免在會議進行中時，不需要管理可能較大的大廳。
    
      - 如果會議是僅限內部會議，請將會議存取類型設定為 [**我的組織中的任何人**]。
        
        <div>
        

        > [!NOTE]  
        > 避免將 [會議存取類型] 設定為 [<STRONG>我從公司邀請的人員</STRONG>]，因為當您使用此設定時，召集人必須將所有使用者電子郵件地址新增至被邀請者清單，而且您無法邀請通訊群組。<BR>避免將會議存取類型設定為<STRONG>[僅自己] （會議召集人），</STRONG>因為這項設定需要每個會議參與者（包括簡報者）都必須放在會議執行時間的大廳中。 負責執行大型會議的人員必須持續監視大廳名單並承認大廳中的新使用者。

        
        </div>

  - [允許從手機撥入的使用者] 透過核取 [來電者**直接取得**] 設定來自動進入會議。

  - 明確邀請下列使用者：
    
      - 會議召集人和委派（申請者）
    
      - 會議申請者提供的簡報者清單
    
    <div>
    

    > [!NOTE]  
    > 如果 [會議存取類型] 設定為<STRONG>[我選擇的人員</STRONG>]，您必須明確將大型會議的參與者新增為會議的被邀請者。

    
    </div>

  - 明確管理簡報者，而不是將簡報者選項設定為其中一個自動升級值。 請務必將下列使用者新增為簡報者：
    
      - 會議召集人和委派（申請者）
    
      - 大型會議申請者提供的簡報者清單
    
    <div>
    

    > [!NOTE]  
    > 透過顯式管理簡報者，您可以控制簡報者的數目，讓您可以將簡報者限制為小數位，以讓其擁有有效的大型會議。 如果大多數會議參與者都有出席者角色，這有助於減少人員不小心控制簡報的機率、刪除 PowerPoint 簡報、靜音/unmuting 簡報者，以及其他中斷會議的機會。

    
    </div>

  - 核取 [**所有出席者靜音**] 設定，以確保只有簡報者可以將音訊廣播到會議中。

  - 核取 [**封鎖出席者的影片**] 設定，以確保只有簡報者可以將影片廣播到會議中。

下圖顯示適用于 Lync 之線上會議增益集的建議設定。

![54e4e70d-06b0-45cd-8d94-bab649cd5dc0](images/JJ204823.54e4e70d-06b0-45cd-8d94-bab649cd5dc0(OCS.15).jpg "54e4e70d-06b0-45cd-8d94-bab649cd5dc0")

</div>

<span> </span>

</div>

</div>

</div>

