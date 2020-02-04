---
title: Lync Server 2013：發行更新後的拓撲
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
ms.openlocfilehash: 4500d12c7b0a054ccce910f27c80f9aaa83eccaf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747063"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publish-the-updated-topology-in-lync-server-2013"></a>在 Lync Server 2013 中發行更新後的拓撲

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-01_

在拓撲建立器中更新拓撲之後，您必須先將拓撲發佈到中央管理儲存區，才能設定及使用持續聊天伺服器。 唯讀複本會將資料複製到拓撲中的所有伺服器，以讓所有伺服器與拓撲和其他設定變更保持同步。

<div>

## <a name="to-publish-an-updated-topology"></a>發佈已更新的拓撲

在發佈拓撲前，請先安裝持久聊天伺服器的資料庫。 使用拓撲建立器，選取 [**動作**] 並**安裝資料庫**以安裝資料庫。

1.  在執行 Lync Server 2013 或已安裝 Lync Server 管理工具的電腦上，使用 [**網域系統管理員**] 群組和 [ **RTCUniversalServerAdmins** ] 群組成員的帳戶登入，並在檔案存放區上擁有 [完全控制] 許可權（也就是讀取、寫入及修改），以用於持續聊天伺服器檔案存放區（以便讓拓撲產生器可以設定必要的隨機存取控制清單（dacl）），或是具有同等使用者權限的帳戶。

2.  啟動拓撲建立器。 選取 [**從現有部署下載拓朴**]，或**從本機檔案中開啟拓撲**（如果您在本機上儲存）。

3.  在主控台樹中，以滑鼠右鍵按一下 [ **Lync Server 2013**]，然後按一下 [**發佈拓撲**]。

4.  在 [**發佈拓撲**] 頁面上，按一下 **[下一步]**。

5.  在 [**發佈嚮導完成]** 頁面上，確認拓撲已順利發佈，然後按一下 **[完成]**。
    
    <div>
    

    > [!IMPORTANT]  
    > 發佈拓朴之後，您必須先設定持久聊天伺服器的支援，才能封存任何內容。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

