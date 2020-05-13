---
title: Lync Server 2013：建立或編輯主控的 SIP 同盟提供者
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or edit hosted SIP federated providers
ms:assetid: 0dd6dcb6-a88d-46b8-9c96-b35967309bcd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552445(v=OCS.15)
ms:contentKeyID: 48679556
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b78e9be0f3b885a40fcf313173a1281ac5489936
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221837"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-edit-hosted-sip-federated-providers-lync-server-2013"></a>建立或編輯主控的 SIP 同盟提供者 Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-19_

主控提供者立即訊息（IM）連線功能可讓您組織中的使用者使用 IM，與託管提供者提供的 IM 服務使用者通訊，包括 Microsoft 365 和 Lync Online。

每個裝載提供者都設有提供者的 Edge Server 完整網域名稱，以及預設驗證層級 [允許使用者僅與其連絡人清單中使用此提供者的人通訊]****。

使用下列程序來建立或編輯裝載提供者：

<div>

## <a name="to-create-or-edit-hosted-providers"></a>建立或編輯裝載提供者

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶（或具有相等的使用者權限）或指派給 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱[Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中，按一下 [同盟及外部存取]****，然後按一下 [SIP 同盟提供者]****。

4.  如果您需要建立新的裝載提供者，請按一下 [新增]****，然後按一下 [裝載提供者]****。

5.  如果您需要編輯裝載提供者清單中的項目，請選取裝載提供者，按一下 [編輯]****，然後按一下 [顯示詳細資料]****。

6.  在「編輯 SIP 同盟提供者」**** 頁面上，您可以輸入或編輯下列設定：
    
      - **啟用與此提供者**     的通訊選取此設定便可與此提供者的使用者進行通訊。
    
      - **提供者名稱：**    必要的屬性，請輸入提供者的名稱，因為它會反映在 SIP 同盟提供者的清單中。
    
      - **Access Edge service （FQDN）：**    必要的屬性，請輸入您要設定之主控提供者的 Access Edge service 的完整功能變數名稱。 此資訊應由主控的提供者提供，而且只有在主控提供者對主控提供者的 Access Edge service 的 FQDN 進行變更時，才應變更此資訊。
    
      - **預設驗證層級：**    預設設定為 [**允許使用者與使用此提供者的連絡人清單上的人員通訊**]，會限制對您已接受的連絡人和連絡人清單中的連絡人進行通訊。
        
        選取 [允許使用者與使用此提供者的所有人通訊]**** 會移除您必須收到並接受連絡人邀請的限制。此設定不限制哪些人可以從裝載提供者的網路連絡您。

7.  完成設定時，按一下 [認可]**** 以儲存，或按一下 [取消]**** 以捨棄變更。

</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中設定原則以控制公用使用者存取](lync-server-2013-configure-policies-to-control-public-user-access.md)  
[在 Lync Server 2013 中啟用或停用同盟與公用 IM 連線](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

