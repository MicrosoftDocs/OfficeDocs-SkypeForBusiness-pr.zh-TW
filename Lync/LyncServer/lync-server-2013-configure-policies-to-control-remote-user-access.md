---
title: Lync Server 2013：設定原則以控制遠端使用者存取
description: Lync Server 2013：設定原則以控制遠端使用者存取。
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
ms.openlocfilehash: 6408747cfbbc5e7dff8fd198c0de162f49fc5ff2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548709"
---
# <a name="configure-policies-to-control-remote-user-access-in-lync-server-2013"></a>在 Lync Server 2013 中設定控制遠端使用者存取的原則

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-18_

您可以設定一或多個外部使用者存取原則，以控制遠端使用者是否可以與內部 Lync Server 使用者共同作業。 若要控制遠端使用者存取，您可以在全域、網站及使用者層級設定原則。 網站原則會覆寫全域原則，而使用者原則會覆寫網站和全域原則。 如需您可以設定之原則類型的詳細資訊，請參閱 [管理 Lync Server 2013 的同盟與外部存取](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md)。 套用於一個原則層級的 Lync Server 原則設定可以覆寫在另一個原則層級套用的設定。 Lync Server 原則優先順序是：使用者原則 (最大的影響) 覆寫網站原則，然後網站原則會覆寫全域原則 (最小影響) 。 也就是說，原則設定愈接近原則影響的物件，對物件所造成的影響也越大。

<div>


> [!NOTE]  
> 即使您沒有為組織啟用遠端使用者存取，您也可以設定原則來控制遠端使用者存取。 不過，您設定的原則只有當您為組織啟用遠端使用者存取時才會生效。 如需啟用遠端使用者存取的詳細資訊，請參閱 <A href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and PUBLIC IM connectivity In Lync Server 2013</A>。 此外，如果您指定用來控制遠端使用者存取的使用者原則，此原則只適用于已啟用 Lync Server 且設定為使用原則的使用者。 如需指定可以從遠端位置登入 Lync Server 之使用者的詳細資訊，請參閱 <A href="lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md">將外部使用者存取原則指派給 Lync server 2013 中啟用 lync 功能的使用者</A>。



</div>

使用下列程式可設定每個要用來控制遠端使用者存取的外部存取原則。

<div>


> [!NOTE]  
> 此程式說明如何設定原則，只啟用與遠端使用者的通訊，但設定為支援遠端使用者存取的每個原則也可以設定同盟使用者存取和公用使用者存取。 如需設定支援同盟使用者之原則的詳細資訊，請參閱 <A href="lync-server-2013-configure-policies-to-control-federated-user-access.md">在 Lync Server 2013 中設定控制同盟使用者存取的原則</A>。 如需設定原則以支援公用使用者的詳細資訊，請參閱 <A href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">在 Lync Server 2013 中建立或編輯公用 SIP 同盟提供者</A>。



</div>

<div>

## <a name="to-configure-an-external-access-policy-to-support-remote-user-access"></a>設定外部存取原則以支援遠端使用者存取

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中，依序按一下 [外部使用者存取]**** 及 [外部存取原則]****。

4.  在「外部存取原則」**** 頁面中，執行下列其中一項：
    
      - 若要設定全域原則以支援遠端使用者存取，請按一下全域原則，按一下 [ **編輯**]，然後按一下 [ **顯示詳細資料**]。
    
      - 若要建立新的網站原則，請按一下 **[新增]**，然後按一下 **[站台原則]**。在 **[選取站台]** 的清單中按一下適當網站，然後按一下 **[確定]**。
    
      - 若要建立新的使用者原則，按一下 **[新增]**，再按一下 **[使用者原則]**。 在 [ **新增外部存取原則**] 中，在 [ **名稱** ] 欄位中建立唯一的名稱，以指出使用者原則所涵蓋的內容 (例如，針對為遠端使用者) 啟用通訊的使用者原則，請 **EnableRemoteUsers** 。
    
      - 若要變更現有原則，按一下表中所列之適當原則，然後按一下 [編輯]****，接著按一下 [顯示詳細資料]****。

5.  (選用) 如果您想要新增或編輯說明，請在 [說明]**** 中指定原則資訊。

6.  執行下列其中一項作業：
    
      - 若要啟用原則的遠端使用者存取，請選取 [ **啟用與遠端使用者的通訊** ] 核取方塊。
    
      - 若要停用原則的遠端使用者存取，請清除 [ **啟用與遠端使用者的通訊** ] 核取方塊。

7.  按一下 **[認可]**。

若要啟用遠端使用者存取，您也必須啟用組織中遠端使用者存取的支援。 如需詳細資訊，請參閱部署檔或作業檔中的 [Enable 或 disable federation and PUBLIC IM connectivity In Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) 。

如果這是使用者原則，您也必須將原則套用至您要能夠遠端連線的使用者。 如需詳細資訊，請參閱部署檔或作業檔中的 [指派外部使用者存取原則給 Lync Server 2013 中的 lync 啟用使用者](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md) 。

</div>

</div>

<span> </span>

</div>

</div>

</div>

