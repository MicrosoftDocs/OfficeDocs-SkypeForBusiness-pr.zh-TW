---
title: Lync Server 2013：設定原則以控制公用使用者存取
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure policies to control public user access
ms:assetid: 090aea0f-ef0b-49da-9c80-02d9279f2fa6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520946(v=OCS.15)
ms:contentKeyID: 48183343
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e259082aa73d4354e8e4aa93eb7a0cc8d7ed7a6e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978374"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-policies-to-control-public-user-access-in-lync-server-2013"></a>在 Lync Server 2013 中設定原則以控制公用使用者存取

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-10-07_

公用立即訊息（IM）連線功能可讓貴組織中的使用者使用 IM 與公用 IM 服務提供者所提供之 IM 服務的使用者通訊，包括 Internet 服務、Yahoo\!和 AOL 提供的 Windows Live 網路。 您可以設定一或多個外部使用者存取原則，以控制公用使用者是否可與內部 Lync 伺服器使用者共同作業。 公用立即訊息連線能力是一項額外的功能，可依賴您的部署與使用者的設定。 它也取決於在公用 IM 提供者上提供服務的功能。 如需如何將您的部署設定為使用公用提供者的相關資訊，請參閱「適用于 Microsoft Lync Server、Office 通訊伺服器與即時通訊伺服器的公用 IM 連線設定指南」指南：[http://go.microsoft.com/fwlink/?LinkId=269821](http://go.microsoft.com/fwlink/?linkid=269821)

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>從2012年9月1日起，Microsoft Lync 公用 IM 連線使用者訂閱授權（「PIC USL」）已不再提供購買新或續約協定的功能。 擁有作用中授權的客戶將能夠繼續與 Yahoo！進行聯盟 信使，直到服務關閉日期為止。 AOL 和 Yahoo！的存留期結束日期為2014年6月 已公佈。 如需詳細資訊，請參閱<A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的公用立即信使連線支援</A>。</P>
> <LI>
> <P>PIC USL 是 Lync Server 或 Office 通訊伺服器要與 Yahoo！聯盟時所需的每個使用者每月訂閱授權 名單. Microsoft 提供此服務的能力已因 Yahoo！的支援而定，並向下纏繞的基礎協定。</P>
> <LI>
> <P>Lync 是一種功能強大的工具，可跨組織與世界各地的人員連線。 與 Windows Live Messenger 的同盟不需要在 Lync 標準 CAL 以外的其他使用者/裝置授權。 您可以在這個清單中新增 Skype 同盟，讓 Lync 使用者能夠使用 IM 和語音來與成百上千的人取得聯繫。</P></LI></UL>



</div>

若要存取 Microsoft Lync Server 公用 IM 連線提供網站，請使用下列連結：[http://go.microsoft.com/fwlink/p/?linkId=212638](http://go.microsoft.com/fwlink/p/?linkid=212638)

若要控制公用使用者的存取權，您可以在全域、網站和使用者層級設定原則。 如需有關您可以設定之原則類型的詳細資料，請參閱在部署檔或規劃檔中，設定[Lync Server 2013 中的外部使用者存取支援](lync-server-2013-configuring-support-for-external-user-access.md)。 在一個策略層級套用的 Lync Server 原則設定，可以覆寫在其他原則層級套用的設定。 Lync 伺服器策略優先順序為：使用者原則（最大影響）會覆寫網站原則，然後網站原則會覆寫全域原則（最小的影響）。 這表示原則設定越接近策略設定的物件，就會受到對物件的影響。

在 IM 邀請的情況下，回應會視用戶端軟體而定。 除非由使用者設定的規則明確封鎖外部寄件者（也就是使用者的用戶端**允許**及**封鎖**清單中的設定），否則就會接受該要求。 此外，如果使用者想要封鎖來自不在其 [**允許**] 清單中的使用者的所有 IM，也可以封鎖 im 邀請。

<div>


> [!NOTE]  
> 您可以設定原則來控制公用使用者的存取，即使您的組織未啟用同盟也一樣。 不過，您設定的原則只會在您的組織啟用同盟時生效。 如需啟用同盟的詳細資料，請參閱在部署檔或操作檔中<A href="lync-server-2013-enable-or-disable-remote-user-access.md">啟用或停用 Lync Server 2013 中的遠端使用者存取</A>。 此外，如果您指定使用者原則來控制公用使用者存取，則原則只適用于已啟用 Lync Server 且設定為使用原則的使用者。 如需指定可以登入 Lync Server 之公用使用者的詳細資料，請參閱在部署檔或操作檔中，<A href="lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md">將外部使用者存取原則指派給 Lync server 2013 中的 lync 啟用使用者</A>。



</div>

使用下列程式來設定原則，以支援由一或多個公用 IM 提供者的使用者存取。

<div>

## <a name="to-configure-an-external-access-policy-to-support-public-user-access"></a>設定外部存取原則以支援公用使用者存取

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**外部使用者存取**]，然後按一下 [**外部存取原則**]。

4.  在 [**外部存取原則**] 頁面上，執行下列其中一項操作：
    
      - 若要設定全域原則以支援公用使用者存取，請按一下全域原則，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**]。
    
      - 若要建立新的網站原則，請按一下 [**新增**]，然後按一下 [**網站原則**]。 在 [**選取網站**] 中，從清單中按一下適當的網站，然後按一下 **[確定]**。
    
      - 若要建立新的使用者原則，請按一下 [**新增**]，然後按一下 [**使用者原則**]。 在**新的外部存取原則**中，在 [name] （**名稱**）欄位中建立唯一的名稱，以指出使用者原則所涵蓋的內容（例如，可為公用使用者進行通訊的使用者原則的**EnablePublicUsers** ）。
    
      - 若要變更現有的原則，請按一下表格中所列的適當原則，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**]。

5.  可選如果您想要新增或編輯描述，請在 [**描述**] 中指定原則的資訊。

6.  請執行下列其中一項操作：
    
      - 若要針對原則啟用公用使用者存取，請選取 [**啟用與公用使用者的通訊**] 核取方塊。
    
      - 若要停用公用使用者對原則的存取權，請清除 [**啟用與公用使用者的通訊**] 核取方塊。

7.  按一下 [認可]****。

若要啟用公用使用者存取，您也必須在您的組織中啟用同盟支援。 如需詳細資訊，請參閱[在 Lync Server 2013 中設定控制聯盟使用者存取權的原則](lync-server-2013-configure-policies-to-control-federated-user-access.md)。

如果這是使用者原則，您也必須將原則套用到您想要能夠與公用使用者共同作業的公用使用者。 如需詳細資訊，請參閱[在 Lync Server 2013 中指派每個使用者的原則](lync-server-2013-assigning-per-user-policies.md)。

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中建立或編輯公用 SIP 同盟提供者](lync-server-2013-create-or-edit-public-sip-federated-providers.md)  


[在 Lync Server 2013 中管理組織的 SIP 同盟提供者](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

