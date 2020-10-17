---
title: Lync Server 2013：建立新的 Web 服務設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create new Web Service configuration settings
ms:assetid: f3f04d81-8a1f-427f-bd0f-fb659024e096
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182605(v=OCS.15)
ms:contentKeyID: 48185801
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2d44e86ad1d587bd3dddb921cdeea3ed2a65ea26
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515570"
---
# <a name="create-new-web-service-configuration-settings-in-lync-server-2013"></a>在 Lync Server 2013 中建立新的 Web 服務設定

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

您可以使用 [ **Web 服務** ] 頁面來設定驗證方法，以存取 Lync Server 2013 相關的網頁伺服器和 web 服務。

請遵循下列步驟建立新的 Web 服務原則。

<div>

## <a name="to-create-new-web-service-configuration-settings"></a>若要建立新的 web 服務設定

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您已部署 Lync Server 2013 之網路中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中，按一下 [ **安全性** ]，然後按一下 [ **Web 服務**]。

4.  在 [ **Web 服務** ] 頁面上，按一下 [ **新增**]，然後執行下列其中一項動作：
    
      - 若要設定網站的 Web 服務，請按一下 [ **網站**設定]。 在 [ **選取網站**] 中，按一下要套用 Web 服務原則的網站，然後按一下 **[確定]**。
    
      - 若要設定集區的 Web 服務，請按一下 [ **集**區設定]。 在 [ **選取服務**] 中，按一下將套用 Web 服務原則的服務，然後按一下 **[確定]**。

5.  在 **[新的 Web 服務設定**] 的 **整合式 windows 驗證**中，選取 [ **協商**]、[ **整合式 windows 驗證**] 或 [ **無**]。

6.  根據用戶端的功能和您環境中的支援，選取下列其中一項或多項：
    
      - **啟用 Pin 驗證** ，以允許使用 pin 碼驗證用戶端。
    
      - [**啟用憑證驗證**] 以讓集區中的伺服器對用戶端發出憑證。
    
      - [**啟用憑證鏈下載**] 可讓顯示驗證憑證的伺服器下載該憑證的憑證鏈。

7.  按一下 **[認可]**。

</div>

</div>

<span> </span>

</div>

</div>

</div>

