---
title: Lync Server 2013：指派會議原則以支援匿名使用者
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign conferencing policies to support anonymous users
ms:assetid: 662de022-1111-40f7-bad4-f2b686f30973
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521007(v=OCS.15)
ms:contentKeyID: 48184333
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bab1c3da15bd72bb03233ca05d86e355eebbb233
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734073"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assign-conferencing-policies-to-support-anonymous-users-in-lync-server-2013"></a>在 Lync Server 2013 中指派會議原則以支援匿名使用者

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-19_

根據預設，所有使用者都會被禁止邀請匿名使用者參與會議。 您可以將會議原則設定為支援匿名使用者，並將該會議原則套用到特定使用者，以控制誰能邀請匿名使用者。 如需有關如何設定會議原則以支援匿名使用者的詳細資料，請參閱[在 Lync server 2013 中建立或修改會議原則](lync-server-2013-create-or-modify-a-conferencing-policy.md)，以及[管理 lync server 2013 的同盟與外部存取](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md)。

使用本節中的程式，將您已建立的會議原則套用至一或多個使用者或使用者群組。

<div>


> [!NOTE]  
> 除了設定及套用原則以讓使用者邀請匿名使用者，您也必須為貴組織啟用匿名使用者支援。 如需詳細資訊，請參閱<A href="lync-server-2013-configure-policies-to-control-public-user-access.md">在 Lync Server 2013 中設定控制公用使用者存取的原則</A>。



</div>

<div>

## <a name="to-configure-a-user-policy-for-anonymous-participation-in-meetings"></a>設定匿名參與會議的使用者原則

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**會議**]，然後執行下列其中一項操作：
    
    1.  若要建立新的使用者原則，請按一下 [**新增**]，然後按一下 [**使用者原則**]。 在 [Name] （**名稱**）欄位中建立唯一的名稱，以指出使用者原則所涵蓋的內容（例如，允許與匿名使用者進行通訊的使用者原則**EnableAnonymous** ）。
    
    2.  若要設定現有的使用者原則，請按一下表格中所列的適當原則，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**]。

4.  在 [**會議原則**] 對話方塊中，選取 [**允許參與者邀請匿名使用者**] 核取方塊。

5.  按一下 [認可]****。

6.  在左側導覽列中，按一下 [**使用者**]，搜尋您要設定的使用者帳戶。

7.  在列出搜尋結果的表格中，依序按一下使用者帳戶、[編輯]**** 及 [顯示詳細資料]****。

8.  在 [**會議原則**] 下的 [**編輯 Lync Server 使用者**] 中，選取您要套用至此使用者之 [匿名使用者存取設定] 的使用者原則。
    
    <div>
    

    > [!NOTE]  
    > [ <STRONG> &lt;自動&gt; </STRONG>設定] 會套用預設伺服器安裝設定，且由伺服器自動套用。

    
    </div>

若要讓使用者邀請匿名使用者加入會議，您也必須在組織中啟用匿名使用者支援。 如需詳細資訊，請參閱在部署檔或操作檔中，[設定控制在 Lync Server 2013 中的公用使用者存取的原則](lync-server-2013-configure-policies-to-control-public-user-access.md)。

</div>

</div>

<span> </span>

</div>

</div>

</div>

