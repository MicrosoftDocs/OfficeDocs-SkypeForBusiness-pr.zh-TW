---
title: Lync Server 2013： 發佈更新過的拓撲
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publish the updated topology
ms:assetid: 59455dd1-6a9e-433f-a714-d3636c068100
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204910(v=OCS.15)
ms:contentKeyID: 48184203
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5a0a690d38d6f7d348cdaf12503b08027bc4c0f4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2020
ms.locfileid: "41987318"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publish-the-updated-topology-in-lync-server-2013"></a>在 Lync Server 2013 中發佈更新過的拓撲

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-01_

在更新之後您在拓撲產生器的拓撲，您必須中央管理存放區發行拓撲，您可以設定及使用 Persistent Chat Server 之前。 資料的唯讀複本會複寫到拓撲中的所有伺服器，讓所有伺服器與拓撲和其他設定變更保持同步。

<div>

## <a name="to-publish-an-updated-topology"></a>發行更新的拓撲

發行拓撲之前，請安裝 Persistent Chat Server 資料庫。 使用拓撲產生器來選取**巨集指令**並**安裝資料庫**，來安裝資料庫。

1.  找出是執行 Lync Server 2013 或在 Lync Server 系統管理工具安裝上使用為**Domain Admins**群組和**RTCUniversalServerAdmins**群組的成員帳戶登入和用於 Persistent Chat Server 檔案存放區 （以便拓撲產生器可以設定必要的判別存取控制清單 (Dacl)） 的檔案存放區上具有完整控制權限 （亦即，讀取、 寫入及修改） 的電腦上，或具有相等使用者權限的帳戶。

2.  啟動拓撲產生器]。 選取 **[從現有的部署下載拓撲]**，若您已將拓撲儲存在本機上，可選取 **[從本機檔案開啟拓撲]**。

3.  在主控台樹狀目錄中，以滑鼠右鍵按一下 [ **Lync Server 2013**中，，，然後按一下 [**發行拓撲**。

4.  在 **[發行拓撲]** 頁面上，按 **[下一步]**。

5.  在 **[發行精靈完成]** 頁面上，確認拓撲已成功發行，然後按一下 **[完成]**。
    
    <div>
    

    > [!IMPORTANT]  
    > 發行拓撲之後, 您必須設定支援 for Persistent Chat Server 之前可以封存任何內容。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

