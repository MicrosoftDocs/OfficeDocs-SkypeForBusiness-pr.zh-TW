---
title: Lync Server 2013：發行更新的拓撲
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
ms.openlocfilehash: 2f696b06f317ac20b98a14734f1eaf076105dbd8
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512310"
---
# <a name="publish-the-updated-topology-in-lync-server-2013"></a>在 Lync Server 2013 中發佈更新的拓撲

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-01_

在拓撲產生器中更新拓撲之後，您必須將拓撲發行至中央管理存放區，才能設定及使用 Persistent Chat Server。 資料的唯讀複本會複寫到拓撲中的所有伺服器，讓所有伺服器與拓撲和其他設定變更保持同步。

<div>

## <a name="to-publish-an-updated-topology"></a>發行更新的拓撲

在發佈拓撲之前，請安裝 Persistent Chat Server 的資料庫。 使用拓撲產生器，選取 [ **動作** ] 並 **安裝資料庫**以安裝資料庫。

1.  在執行 Lync Server 2013 的電腦上，或安裝 Lync Server 系統管理工具的電腦上，使用 **Domain Admins** 群組和 **RTCUniversalServerAdmins** 群組的成員帳戶進行登入。而且具有要用於 Persistent Chat Server 檔存放區之檔案存放區上的「完全控制」許可權 (（讀取、寫入及修改）) ，所以拓撲產生器可以設定所需的任意自由訪問 (控制清單 (dacl) # A5，或具有同等使用者權限的帳戶。

2.  啟動拓撲產生器。 選取 **[從現有的部署下載拓撲]**，若您已將拓撲儲存在本機上，可選取 **[從本機檔案開啟拓撲]**。

3.  在主控台樹中，以滑鼠右鍵按一下 [ **Lync Server 2013**]，然後按一下 [ **發行拓撲**]。

4.  在 **[發行拓撲]** 頁面上，按 **[下一步]**。

5.  在 **[發行精靈完成]** 頁面上，確認拓撲已成功發行，然後按一下 **[完成]**。
    
    <div>
    

    > [!IMPORTANT]  
    > 發行拓撲之後，您必須先設定 Persistent Chat Server 的支援，才能封存任何內容。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

