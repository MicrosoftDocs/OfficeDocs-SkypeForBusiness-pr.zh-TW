---
title: Lync Server 2013：建立或編輯公用 SIP 同盟提供者
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or edit public SIP federated providers
ms:assetid: 5321598c-1ab1-40e3-b739-4b2e6d0a3a3b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398349(v=OCS.15)
ms:contentKeyID: 48184167
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 58b0ffdc009d48ef82d1bdf3ba8662cd4072ea1c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514850"
---
# <a name="create-or-edit-public-sip-federated-providers-in-lync-server-2013"></a>在 Lync Server 2013 中建立或編輯公用 SIP 同盟提供者

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-19_

公用立即訊息 (IM) 連線能力，讓組織中的使用者能夠使用 IM，與公用 IM 服務提供者所提供的 IM 服務使用者通訊，包括 Windows Live Messenger、Yahoo \! 和 AOL。

Lync Server 2013 具有適用于北美線上、Windows Live 和 Yahoo 的公用提供者設定\! 立即訊息的公用提供者設定。 每個公用提供者都會使用提供者的 Edge Server 完整網域名稱，以及預設驗證層級 **[僅允許使用者與其連絡人清單上使用此提供者的人通訊]** 來設定。

預設設定為不啟用任何公用提供者。 在啟用公用提供者之前，您應該先完成授權合約及佈建工作。 您可以在完成授權和佈建工作之前啟用提供者。 在必要工作完成之前，使用者將無法與這些提供者的連絡人通訊。 如需授權及布建公用提供者的詳細資訊，請參閱 [Configure 原則 to control public user access In Lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md)。

請使用下列程序來建立或編輯公用提供者：

<div>

## <a name="to-create-or-edit-public-providers"></a>建立或編輯公用提供者

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中，依序按一下 **[同盟和外部存取]** 和 **[SIP 同盟提供者]**。

4.  如果您需要建立新的公用提供者，請依序按一下 **[新增]** 和 **[公用提供者]**。

5.  如果您需要編輯公用提供者清單中的項目，選取公用提供者，然後依序按一下 **[編輯]** 和 **[顯示詳細資料]**。

6.  在 **[編輯 SIP 同盟提供者]** 頁面上，您可以鍵入或編輯下列設定：
    
      - **啟用與此提供者**     的通訊選取此設定可讓 IM 使用此提供者的使用者。
    
      - **提供者名稱：**    必要的屬性，請輸入提供者的名稱，因為它會反映在 SIP 同盟提供者的清單中。
    
      - **Access Edge service (FQDN) ：**    必要的屬性，請輸入您要設定之提供者的 Access Edge service 的完整功能變數名稱。 此資訊是以預設專案提供，只在公用提供者對公用提供者的 Access Edge service 的 FQDN 進行變更時，才應變更。
    
      - **預設驗證層級：**    預設設定為 [**允許使用者與使用此提供者的連絡人清單上的人員通訊**]，會限制對您已接受的連絡人和連絡人清單中的連絡人進行通訊。
        
        選取 **[允許使用者與使用此提供者的所有人通訊]** 會移除您必須已收到並接受連絡人邀請的限制。此設定不會限制誰可以從公用提供者網路與您連絡。

7.  完成設定之後，請按一下 **[認可]** 儲存，或按一下 **[取消]** 捨棄您的變更。

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

