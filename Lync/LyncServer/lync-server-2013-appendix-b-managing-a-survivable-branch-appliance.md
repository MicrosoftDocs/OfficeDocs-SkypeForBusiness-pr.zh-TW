---
title: Lync Server 2013：附錄 B：管理 Survivable Branch Appliance
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: 'Appendix B: Managing a Survivable Branch Appliance'
ms:assetid: 2ec9d505-6d39-491c-9524-8cf36866b855
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425797(v=OCS.15)
ms:contentKeyID: 48183773
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e267f81327e9d1f49b81ab0d999c37c02da55b31
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976107"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="appendix-b-managing-a-survivable-branch-appliance-in-lync-server-2013"></a>Lync Server 2013 中的附錄 B：管理 Survivable Branch Appliance

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-18_

本主題說明管理 Survivable 分支裝置的程式。 具體來說，如何取代及重新命名 Survivable 分支裝置，以及如何變更與 Survivable 分支裝置相關聯的 Lync Server 2013 前端池。

<div>

## <a name="to-replace-a-survivable-branch-appliance"></a>若要取代 Survivable 分支裝置

1.  在 Survivable 分支裝置上停止所有 Lync Server 2013 服務。 （請參閱 Survivable 分支裝置供應商檔。）

2.  採用從網域中移除 Survivable 分支裝置。

3.  若要刪除 Active Directory 網域服務中的 Survivable 分支裝置電腦物件，請依照下列步驟執行：
    
      - 以企業系統管理員群組的成員身分登入成員伺服器。
    
      - 按一下 [**開始**]，按一下 [**管理工具**]，然後按一下 [ **Active Directory 使用者和電腦**]。
    
      - 以滑鼠右鍵按一下 [Survivable 分支裝置] 物件，然後按一下 [**刪除**]。

4.  再次新增 Survivable 分支裝置電腦物件。 （請參閱[在 Lync Server 2013 的 Active Directory 中新增 Survivable 分支裝置](lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md)。）

5.  等待 Active Directory 複製發生。

6.  開啟 Lync Server 管理命令介面，然後輸入**Enable-CSTopology**。

7.  將新的 Survivable 分支裝置連線到網路，然後依照[使用 Lync server 2013 部署 Survivable 分支裝置或伺服器](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md)的步驟進行，以使用 lync server [2013-分支網站工作來部署 Survivable 分支裝置或伺服器](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)。

</div>

<div>

## <a name="to-rename-a-survivable-branch-appliance"></a>若要重新命名 Survivable 分支裝置

1.  將使用者移至中心網站。 如需詳細資訊，請參閱[在 Lync Server 2013 中將使用者移至另一個池中](lync-server-2013-move-users-to-another-pool.md)。

2.  在 Survivable 分支裝置上停止所有 Lync Server 2013 服務。 （請參閱 Survivable 分支裝置供應商檔。）

3.  若要從拓撲中移除 Survivable 分支裝置，請遵循下列步驟進行：
    
      - 按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server**]，然後按一下 [ **Lync server 拓撲**建立器]。
    
      - 在主控台樹中，展開 [**分支網站**]，按一下 [Survivable 分支裝置]，然後按一下 [動作] 窗格上的 [**刪除**]。

4.  從網域中移除 Survivable 分支裝置。

5.  若要刪除 Active Directory 中的 Survivable 分支裝置電腦物件，請執行下列步驟：
    
      - 以企業系統管理員群組的成員身分登入網網域控制站。
    
      - 按一下 [**開始**]，按一下 [**管理工具**]，然後按一下 [ **Active Directory 使用者和電腦**]。
    
      - 以滑鼠右鍵按一下 [Survivable 分支裝置] 物件，然後按一下 [**刪除**]。

6.  將 Survivable 分支裝置還原為出廠預設值。 （請參閱 Survivable 分支裝置供應商檔。）

7.  遵循[使用 Lync server 2013 部署 Survivable 分支裝置或伺服器](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md)中的步驟進行-中心網站工作，並[使用 Lync Server 2013 部署 Survivable 分支裝置或伺服器（分支網站工作）](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)。

8.  將使用者移至重新命名的 Survivable 分支裝置。 如需詳細資訊，請參閱[在 Lync Server 2013 中將使用者移至另一個池中](lync-server-2013-move-users-to-another-pool.md)。

</div>

<div>

## <a name="to-change-the-lync-server-front-end-pool-that-the-survivable-branch-appliance-is-associated-with"></a>若要變更 Survivable 分支裝置所關聯的 Lync Server 前端池

1.  從 Survivable 分支裝置將使用者移至中央網站上的 Lync Server 前端池。 如需詳細資訊，請參閱[在 Lync Server 2013 中將使用者移至另一個池中](lync-server-2013-move-users-to-another-pool.md)。

2.  停止 Survivable 分支裝置上的所有 Lync Server 服務。 （請參閱 Survivable 分支裝置供應商檔）。

3.  若要更新 Survivable 分支裝置所關聯的 Lync Server 前端池，請執行下列步驟：
    
      - 按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server**]，然後按一下 [ **Lync server 拓撲**建立器]。
    
      - 展開 [**分支網站**]。
    
      - 以滑鼠右鍵按一下要修改的 Survivable 分支裝置物件，然後按一下 [**編輯屬性**]。
    
      - 在 [復原] 底下，選取要與 Survivable 分支裝置相關聯的新 [前端] 池，然後按 **[下一步]**。
    
      - 在主控台樹中，以滑鼠右鍵按一下新的 Survivable 分支裝置，按一下 [**拓撲**]，然後按一下 [**發佈**]。

4.  在 Survivable 分支裝置上重新開機所有 Lync Server 服務。

5.  測試 Survivable 分支裝置。 如需詳細資訊，請參閱[Lync Server 2013 中的 Survivable 分支裝置或伺服器上的家用使用者](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md)。

6.  將使用者從中央網站的 Lync Server 前端池移至 Survivable 分支裝置。

</div>

</div>

<span> </span>

</div>

</div>

</div>

