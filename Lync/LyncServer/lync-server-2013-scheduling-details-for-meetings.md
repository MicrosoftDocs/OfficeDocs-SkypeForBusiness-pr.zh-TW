---
title: Lync Server 2013： 排程會議詳細資料
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
ms.openlocfilehash: 6537309f8c2a787c94897fa9f529c1abf8fd4791
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42047936"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scheduling-details-for-meetings-in-lync-server-2013"></a>Lync Server 2013 中的會議排程詳細資料

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-04_

在檢查確認於要求的時間沒有排程其他會議之後，處理該要求的大型會議支援人員會在大型會議集區中排程會議。 使用 Lync Server 2013 用戶端執行這項工作，以安裝使用的專用的大型會議集區中的 Lync Server 啟用的使用者認證的 Lync 線上會議增益集。

為了確保最佳使用者體驗，排程大型會議時，請務必以適合會議召集人之需求的適當存取層級及會議設定。 我們建議下列排程中的設定 Lync 會議選項：

  - 針對每場大型會議使用新的會議空間，而非重複使用專用會議空間。

  - 以下列方式指定會議存取層級：
    
      - 如果至少有一位組織外的受邀者，則設定會議存取類型為 **[任何人 (沒有限制)]**。這可避免您在會議進行中還需要管理或許擁擠的大廳。
    
      - 如果會議是純內部會議，則設定會議存取類型為 **[來自我組織的任何人]**。
        
        <div>
        

        > [!NOTE]  
        > 避免設定會議存取類型為 <STRONG>[我公司中受邀請的人員]</STRONG>，因為使用此設定時，召集人必須將所有使用者電子郵件地址新增到受邀者清單中，而且無法邀請通訊群組。<BR>避免設定會議存取類型為 <STRONG>[只限會議召集人自己]</STRONG>，因為此設定需要每位會議參與者 (包括簡報者) 在會議舉行時間聚集在大廳。負責舉行該場大型會議的人員就必須時時監控大廳名冊，准許在大廳的新使用者加入會議。

        
        </div>

  - 核取 **[來電者可直接加入]** 設定，允許以電話撥入的使用者自動加入會議。

  - 明確邀請下列使用者：
    
      - 會議召集人及代理人 (要求者)
    
      - 會議要求者提供的簡報者清單
    
    <div>
    

    > [!NOTE]  
    > 如果會議存取類型設定為 <STRONG>[我選擇的人員]</STRONG>，則必須將大型會議中每位參與者明確新增為會議的受邀者。

    
    </div>

  - 明確管理簡報者，而非將簡報者選項設定為其中一項自動升級值。務必將下列使用者新增為簡報者：
    
      - 會議召集人及代理人 (要求者)
    
      - 大型會議要求者提供的簡報者清單
    
    <div>
    

    > [!NOTE]  
    > 透過明確管理簡報者，您可以控制簡報者的人數，限制簡報者的人數少到足以讓大型會議能有效率地舉行。如果大多數的會議參與者為出席者角色，這有助於降低以下事件的發生機會：人員意外主導簡報、刪除 PowerPoint 簡報、將簡報者靜音/取消靜音，以及其他會議干擾。

    
    </div>

  - 核取 **[將所有出席者設為靜音]** 設定，確保只有簡報者能在會議中廣播音訊。

  - 核取 **[封鎖出席者的視訊]** 設定，確保只有簡報者能在會議中廣播視訊。

下圖顯示 Lync 線上會議增益集的建議的設定。

![54e4e70d-06b0-45cd-8d94-bab649cd5dc0](images/JJ204823.54e4e70d-06b0-45cd-8d94-bab649cd5dc0(OCS.15).jpg "54e4e70d-06b0-45cd-8d94-bab649cd5dc0")

</div>

<span> </span>

</div>

</div>

</div>

