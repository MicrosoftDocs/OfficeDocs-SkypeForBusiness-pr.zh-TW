---
title: Lync Server 2013：附錄 B：管理 Survivable 分支裝置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Appendix B: Managing a Survivable Branch Appliance'
ms:assetid: 2ec9d505-6d39-491c-9524-8cf36866b855
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425797(v=OCS.15)
ms:contentKeyID: 48183773
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 20a766ae86d4c74d874f1db747c137f54cf568d9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523220"
---
# <a name="appendix-b-managing-a-survivable-branch-appliance-in-lync-server-2013"></a>附錄 B：在 Lync Server 2013 中管理 Survivable 分支裝置

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-18_

本主題說明管理 Survivable 分支裝置的程式。 具體而言，如何取代和重新命名 Survivable 分支裝置，以及如何變更與 Survivable Branch 裝置相關聯的 Lync Server 2013 前端集區。

<div>

## <a name="to-replace-a-survivable-branch-appliance"></a>取代 Survivable 分支裝置

1.  停止 Survivable 分支裝置上所有的 Lync Server 2013 服務。  (請參閱 Survivable Branch 裝置廠商檔。 ) 

2.   (建議) 從網域移除 Survivable 分支裝置。

3.  請遵循下列步驟，刪除 Active Directory 網域服務中的 Survivable Branch 裝置電腦物件：
    
      - 以 Enterprise Admins 群組成員的身分，登入成員伺服器。
    
      - 依序按一下 **[開始]**、**[系統管理工具]** 和 **[Active Directory 使用者和電腦]**。
    
      - 以滑鼠右鍵按一下 [Survivable 分支裝置] 物件，然後按一下 [ **刪除**]。

4.  再次新增 Survivable Branch 裝置電腦物件。  (請參閱 [將 Survivable 分支裝置新增至 Active Directory 中的 Lync Server 2013](lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md)。 ) 

5.  等候 Active Directory 複寫進行。

6.  開啟 Lync Server 管理命令介面，然後輸入 **Enable-CSTopology**。

7.  將新的 Survivable 分支裝置連接至網路，然後依照以 [Lync server 2013-中央網站工作部署 Survivable 分支裝置或伺服器](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md) 的步驟進行，並 [部署 Survivable branch 裝置或具有 lync Server 2013 的伺服器-分支網站](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)工作。

</div>

<div>

## <a name="to-rename-a-survivable-branch-appliance"></a>若要重新命名 Survivable 分支裝置

1.  將使用者移至中央網站。 如需詳細資訊，請參閱 [將使用者移至另一個集區中的 Lync Server 2013](lync-server-2013-move-users-to-another-pool.md)。

2.  停止 Survivable 分支裝置上所有的 Lync Server 2013 服務。  (請參閱 Survivable Branch 裝置廠商檔。 ) 

3.  遵循下列步驟，將 Survivable 分支裝置從拓撲中移除：
    
      - 依序按一下 [ **開始**]、[ **所有程式**] 及 [ **Microsoft lync server**]，然後按一下 [ **Lync server 拓撲**產生器]。
    
      - 在主控台樹中，展開 [ **分支網站**]，然後按一下 [Survivable 分支裝置]，然後按一下動作窗格上的 [ **刪除** ]。

4.  從網域中移除 Survivable 分支裝置。

5.  請遵循下列步驟，刪除 Active Directory 中的 Survivable Branch 裝置電腦物件：
    
      - 以 Enterprise Admins 群組成員的身分登入網域控制站。
    
      - 依序按一下 [開始]****、[系統管理工具]**** 及 [Active Directory 使用者及電腦]****。
    
      - 以滑鼠右鍵按一下 [Survivable 分支裝置] 物件，然後按一下 [ **刪除**]。

6.  將 Survivable 分支裝置還原為出廠預設值。  (請參閱 Survivable Branch 裝置廠商檔。 ) 

7.  請遵循 [使用 Lync server 2013-中央網站工作部署 Survivable Branch 裝置或伺服器](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md) 的步驟，並 [部署具有 lync Server 2013 的 Survivable 分支裝置或伺服器-分支網站](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)工作。

8.  將使用者移至重新命名的 Survivable 分支裝置。 如需詳細資訊，請參閱 [將使用者移至另一個集區中的 Lync Server 2013](lync-server-2013-move-users-to-another-pool.md)。

</div>

<div>

## <a name="to-change-the-lync-server-front-end-pool-that-the-survivable-branch-appliance-is-associated-with"></a>變更 Survivable 分支裝置相關聯的 Lync Server 前端集區

1.  將使用者從 Survivable Branch 裝置移至中央網站的 Lync Server 前端集區。 如需詳細資訊，請參閱 [將使用者移至另一個集區中的 Lync Server 2013](lync-server-2013-move-users-to-another-pool.md)。

2.  停止 Survivable 分支裝置上所有的 Lync Server 服務。  (請參閱 Survivable Branch 裝置廠商檔) 。

3.  遵循下列步驟，更新與 Survivable 分支裝置相關聯的 Lync Server 前端集區：
    
      - 依序按一下 [ **開始**]、[ **所有程式**] 及 [ **Microsoft lync server**]，然後按一下 [ **Lync server 拓撲**產生器]。
    
      - 展開 [ **分支網站**]。
    
      - 以滑鼠右鍵按一下要修改的 Survivable 分支裝置物件，然後按一下 [**編輯屬性**]。
    
      - 在 [復原能力] 底下，選取要與 Survivable 分支裝置相關聯的新前端集區，然後按 **[下一步]**。
    
      - 在主控台樹中，以滑鼠右鍵按一下新的 Survivable 分支裝置，按一下 [ **拓撲**]，然後按一下 [ **發佈**]。

4.  重新開機 Survivable 分支裝置上的所有 Lync Server 服務。

5.  測試 Survivable 分支裝置。 如需詳細資訊，請參閱在 [Lync Server 2013 中的 Survivable 分支裝置或伺服器上的家庭使用者](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md)。

6.  將使用者從中央網站的 Lync Server 前端集區移至 Survivable Branch 裝置。

</div>

</div>

<span> </span>

</div>

</div>

</div>

