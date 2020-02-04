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
ms.openlocfilehash: d6c97255ce1dc9fce00d9eca6f358f4c68e1ff8a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740223"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-edit-hosted-sip-federated-providers-lync-server-2013"></a>建立或編輯主控的 SIP 同盟提供者 Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-19_

宿主提供者立即訊息（IM）連線功能可讓貴組織中的使用者使用 IM 與託管提供者所提供的 IM 服務使用者通訊，包括 Microsoft Office 365 和 Lync Online。

每個託管提供者都是以提供者的 Edge 伺服器的完整功能變數名稱進行設定，而且預設驗證層級**可讓使用者只與他們的連絡人清單中使用這個提供者的人通訊**。

使用下列程式來建立或編輯託管提供者：

<div>

## <a name="to-create-or-edit-hosted-providers"></a>建立或編輯託管提供者

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**同盟與外部存取**]，然後按一下 [ **SIP 同盟提供者**]。

4.  如果您需要建立新的託管提供者，請按一下 [**新增**]，然後按一下 [**託管提供者**]。

5.  如果您需要編輯託管提供者清單中的專案，請選取託管提供者，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**]。

6.  在 [**編輯 SIP 聯盟提供者**] 頁面上，您可以輸入或編輯下列設定：
    
      - **啟用與此提供者**   的通訊選取此設定，即可與此提供者的使用者進行通訊。
    
      - **提供者名稱：**   required 屬性，請輸入提供者的名稱，因為它會反映在 SIP 同盟提供者清單中。
    
      - **[存取邊緣服務（FQDN）]：**   [必要] 屬性，請輸入您要設定之託管提供者的存取邊緣服務的完整功能變數名稱。 此資訊應該由託管提供者提供，而且只有在託管提供者對託管提供者的存取邊緣服務的 FQDN 進行變更時，才應進行變更。
    
      - **預設驗證階層：**   預設設定是 [**允許使用者與連絡人清單中的人員通訊]，使用這個提供者**時，會將通訊限制在您已接受的連絡人，並在您的連絡人清單中。
        
        選取 [**允許使用者與使用這個提供者的所有人通訊**]，就會移除您必須收到並接受連絡人邀請的限制。 此設定不會限制誰能從主機託管提供者的網路與您聯繫。

7.  設定完畢後，請按一下 [**認可**] 來儲存，或按一下 [**取消**] 放棄您的變更。

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中設定原則以控制公用使用者存取](lync-server-2013-configure-policies-to-control-public-user-access.md)  
[在 Lync Server 2013 中啟用或停用同盟與公用 IM 連線](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

