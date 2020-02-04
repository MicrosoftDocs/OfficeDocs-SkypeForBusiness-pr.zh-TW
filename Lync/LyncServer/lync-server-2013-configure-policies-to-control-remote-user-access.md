---
title: Lync Server 2013：設定原則以控制遠端使用者存取
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure policies to control remote user access
ms:assetid: 8f556849-692b-44a0-9514-4468fc9a39d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398725(v=OCS.15)
ms:contentKeyID: 48184825
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4d8542e7d64198cb83df58885b9240e07066288d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763265"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-policies-to-control-remote-user-access-in-lync-server-2013"></a>在 Lync Server 2013 中設定原則以控制遠端使用者存取

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-18_

您可以設定一或多個外部使用者存取原則，以控制遠端使用者是否可以與內部 Lync Server 使用者共同作業。 若要控制遠端使用者存取權，您可以在全域、網站和使用者層級設定原則。 網站原則會覆寫全域原則，而使用者原則會覆寫網站和全域原則。 如需有關您可以設定之原則類型的詳細資料，請參閱[管理 Lync Server 2013 的同盟與外部存取](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md)。 在一個策略層級套用的 Lync Server 原則設定，可以覆寫在其他原則層級套用的設定。 Lync 伺服器策略優先順序為：使用者原則（最大影響）會覆寫網站原則，然後網站原則會覆寫全域原則（最小的影響）。 這表示原則設定越接近策略設定的物件，就會受到對物件的影響。

<div>


> [!NOTE]  
> 您可以設定控制遠端使用者存取的原則，即使您的組織未啟用遠端使用者存取權也一樣。 不過，您設定的原則只會在您的組織啟用遠端使用者存取時生效。 如需有關啟用遠端使用者存取權的詳細資料，請參閱<A href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">在 Lync Server 2013 中啟用或停用同盟與公用 IM</A>連線。 此外，如果您指定使用者原則來控制遠端使用者存取，則原則只適用于已啟用 Lync Server 且設定為使用原則的使用者。 如需指定可從遠端位置登入 Lync Server 的使用者的詳細資料，請參閱<A href="lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md">在 Lync server 2013 中將外部使用者存取原則指派給 lync 啟用的使用者</A>。



</div>

使用下列程式來設定您要用來控制遠端使用者存取權的每個外部存取原則。

<div>


> [!NOTE]  
> 這個程式說明如何設定原則，只讓它能夠與遠端使用者通訊，但您設定支援遠端使用者存取的每個原則也都可以設定聯盟使用者存取與公用使用者存取。 如需有關設定支援同盟使用者之原則的詳細資訊，請參閱<A href="lync-server-2013-configure-policies-to-control-federated-user-access.md">在 Lync Server 2013 中設定控制聯盟使用者存取權的原則</A>。 如需有關設定支援公用使用者之原則的詳細資訊，請參閱<A href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">在 Lync Server 2013 中建立或編輯公用 SIP 同盟提供者</A>。



</div>

<div>

## <a name="to-configure-an-external-access-policy-to-support-remote-user-access"></a>設定外部存取原則以支援遠端使用者存取

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**外部使用者存取**]，然後按一下 [**外部存取原則**]。

4.  在 [**外部存取原則**] 頁面上，執行下列其中一項操作：
    
      - 若要設定全域原則以支援遠端使用者存取，請按一下全域原則，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**]。
    
      - 若要建立新的網站原則，請按一下 [**新增**]，然後按一下 [**網站原則**]。 在 [**選取網站**] 中，從清單中按一下適當的網站，然後按一下 **[確定]**。
    
      - 若要建立新的使用者原則，請按一下 [**新增**]，然後按一下 [**使用者原則**]。 在**新的外部存取原則**中，在 [name] （**名稱**）欄位中建立一個代表使用者原則所涵蓋內容的唯一名稱（例如，為遠端使用者啟用通訊的使用者原則的**EnableRemoteUsers** ）。
    
      - 若要變更現有的原則，請按一下表格中所列的適當原則，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**]。

5.  可選如果您想要新增或編輯描述，請在 [**描述**] 中指定原則的資訊。

6.  請執行下列其中一項操作：
    
      - 若要啟用此原則的遠端使用者存取權，請選取 [**啟用與遠端使用者的通訊**] 核取方塊。
    
      - 若要停用遠端使用者對原則的存取權，請清除 [**啟用與遠端使用者的通訊**] 核取方塊。

7.  按一下 [認可]****。

若要啟用遠端使用者存取，您也必須在您的組織中啟用遠端使用者存取的支援。 如需詳細資訊，請參閱在部署檔或操作檔中[啟用或停用 Lync Server 2013 中的同盟與公用 IM](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)連線。

如果這是使用者原則，您也必須將原則套用到您想要能夠遠端連線的使用者。 如需詳細資訊，請參閱在部署檔或操作檔中，[將外部使用者存取原則指派給 Lync Server 2013 中的 lync 啟用使用者](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)。

</div>

</div>

<span> </span>

</div>

</div>

</div>

