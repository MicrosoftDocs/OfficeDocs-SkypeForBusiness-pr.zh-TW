---
title: Lync Server 2013：設定原則以控制公用使用者存取
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure policies to control public user access
ms:assetid: 090aea0f-ef0b-49da-9c80-02d9279f2fa6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520946(v=OCS.15)
ms:contentKeyID: 48183343
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a967f186d924a199b007ceba8390bf968253ec72
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520410"
---
# <a name="configure-policies-to-control-public-user-access-in-lync-server-2013"></a>在 Lync Server 2013 中設定原則以控制公用使用者存取

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-10-07_

公用立即訊息 (IM) 連線功能，讓組織中的使用者能夠使用 IM 與公用 IM 服務提供者所提供的 IM 服務使用者通訊，包括 Internet 服務、Yahoo 和 AOL 的 Windows Live 網路 \! 。 您可以設定一或多個外部使用者存取原則，以控制公用使用者是否可以與內部 Lync Server 使用者共同作業。 公用立即訊息連線功能是一項附加的功能，可依賴您的部署和使用者的設定。 它也取決於公用 IM 提供者的服務布建。 如需如何布建部署以使用公用提供者的詳細資訊，請參閱《 Microsoft Lync Server、Office 通訊伺服器和即時通訊伺服器的公用 IM 連線布建指南》指南： [https://go.microsoft.com/fwlink/?LinkId=269821](https://go.microsoft.com/fwlink/?linkid=269821)

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>從2012年9月1日起，Microsoft Lync Public IM 連線使用者訂閱授權 ( 「PIC USL」 ) 不再提供購買新的或更新的協定。 具有使用中授權的客戶將可以繼續與 Yahoo！進行聯盟 信使直到服務關閉日期。 AOL 和 Yahoo！的循環結束日期為2014年6月 已宣告。 如需詳細資訊，請參閱 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">支援 Lync Server 2013 中的公用立即信使</A>連線。</P>
> <LI>
> <P>PIC USL 是 Lync Server 或 Office 通訊伺服器與 Yahoo！進行同盟所需的個別使用者每個月訂閱授權 信使。 Microsoft 提供此服務的能力已因 Yahoo！中的支援而產生，其所向下纏繞的底層合約。</P>
> <LI>
> <P>Lync 是一種強大的工具，可跨組織和世界各地的個人進行連線。 與 Windows Live Messenger 的同盟需要 Lync Standard CAL 以外的其他使用者/裝置授權。 隨即會將 Skype 同盟新增至此清單，讓 Lync 使用者可以使用 IM 和語音來傳送成百上千的人員。</P></LI></UL>



</div>

若要存取 Microsoft Lync Server 公用 IM 連線布建網站，請使用下列連結： [https://go.microsoft.com/fwlink/p/?linkId=212638](https://go.microsoft.com/fwlink/p/?linkid=212638)

若要控制公用使用者存取權，您可以在全域、網站和使用者層級設定原則。 如需您可以設定之原則類型的詳細資訊，請參閱部署檔或規劃檔中的在 [Lync Server 2013 中設定外部使用者存取的支援](lync-server-2013-configuring-support-for-external-user-access.md) 。 套用於一個原則層級的 Lync Server 原則設定可以覆寫在另一個原則層級套用的設定。 Lync Server 原則優先順序是：使用者原則 (最大的影響) 覆寫網站原則，然後網站原則會覆寫全域原則 (最小影響) 。 也就是說，原則設定愈接近原則影響的物件，對物件所造成的影響也越大。

在 IM 邀請方面，回應將視用戶端軟體而定。除非使用者設定的規則 (亦即，在使用者用戶端的 [允許]**** 和 [封鎖]**** 清單中) 明確封鎖外部傳送者，否則會接受要求。另外，如果使用者已選擇封鎖所有不在其 [允許]**** 清單內的 IM 使用者，IM 邀請也會遭到封鎖。

<div>


> [!NOTE]  
> 即便您並未對所屬組織啟用同盟關係，仍可設定原則來控制公用使用者存取。 不過，只有當您為組織啟用同盟關係時，所設定的原則才會生效。 如需啟用同盟的詳細資訊，請參閱部署檔或作業檔中的 <A href="lync-server-2013-enable-or-disable-remote-user-access.md">啟用或停用 Lync Server 2013 中的遠端使用者存取</A> 。 此外，如果您指定用來控制公用使用者存取的使用者原則，此原則只適用于已啟用 Lync Server 且設定為使用原則的使用者。 如需指定可登入 Lync Server 之公用使用者的詳細資訊，請參閱部署檔或作業檔中的 <A href="lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md">指派外部使用者存取原則給 Lync server 2013 中的 lync 啟用使用者</A> 。



</div>

請使用下列步驟來設定原則，以支援一個或多個公用 IM 提供者的使用者存取。

<div>

## <a name="to-configure-an-external-access-policy-to-support-public-user-access"></a>設定外部存取原則以支援公用使用者存取

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中，依序按一下 [外部使用者存取]**** 及 [外部存取原則]****。

4.  在「外部存取原則」**** 頁面中，執行下列其中一項：
    
      - 若要設定全域原則以支援公用使用者存取，依序按一下全域原則、[編輯]**** 和 [顯示詳細資料]****。
    
      - 若要建立新的網站原則，請按一下 [新增]****，然後按一下 [站台原則]****。在 [選取站台]**** 的清單中按一下適當網站，然後按一下 [確定]****。
    
      - 若要建立新的使用者原則，按一下 [新增]****，再按一下 [使用者原則]****。在 [新的外部存取原則]**** 中，於 [名稱]**** 欄位中建立唯一名稱以代表使用者原則的涵蓋範圍 (例如，建立 **EnablePublicUsers** 的使用者原則以啟用公用使用者的通訊功能)。
    
      - 若要變更現有原則，按一下表中所列之適當原則，然後按一下 [編輯]****，接著按一下 [顯示詳細資料]****。

5.  (選用) 如果您想要新增或編輯說明，請在 [說明]**** 中指定原則資訊。

6.  執行下列其中一項作業：
    
      - 若要啟用原則的公用使用者存取功能，請選取 [啟用與公用使用者的通訊]**** 核取方塊。
    
      - 若要停用原則的公用使用者存取功能，請清除 [啟用與公用使用者的通訊]**** 核取方塊。

7.  按一下 **[認可]**。

若要啟用公用使用者存取功能，則您必須同時對組織啟用同盟關係支援。 如需詳細資訊，請參閱 [Configure 原則 to control 同盟 user access In Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md)。

如果這是使用者原則，您也必須將該原則套用至您希望能夠與公用使用者共同作業的公用使用者。 如需詳細資訊，請參閱 [在 Lync Server 2013 中指派每個使用者的原則](lync-server-2013-assigning-per-user-policies.md)。

</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中建立或編輯公用 SIP 同盟提供者](lync-server-2013-create-or-edit-public-sip-federated-providers.md)  


[在 Lync Server 2013 中管理組織的 SIP 同盟提供者](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

