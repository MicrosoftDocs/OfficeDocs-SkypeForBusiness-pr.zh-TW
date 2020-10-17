---
title: Lync Server 2013：修改現有的 Web 服務設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify existing Web Service configuration settings
ms:assetid: bd9c7aa5-d31c-4fab-b31d-8baae26b1296
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182580(v=OCS.15)
ms:contentKeyID: 48185272
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 675cc97e8e16f4e8734f56a9d666b976606c4d2b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534342"
---
# <a name="modify-existing-web-service-configuration-settings-in-lync-server-2013"></a>在 Lync Server 2013 中修改現有的 Web 服務設定

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

您可以使用 [ **Web 服務** ] 頁面來設定驗證方法，以存取 Lync Server 2013 相關的網頁伺服器和 web 服務。

請遵循下列步驟來修改現有的 Web 服務原則。

<div>

## <a name="to-modify-existing-web-service-configuration-settings"></a>修改現有的 Web 服務設定

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您已部署 Lync Server 2013 之網路中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中，按一下 [ **安全性** ]，然後按一下 [ **Web 服務**]。

4.  在 [ **Web 服務** ] 頁面上，按一下設定，然後按一下 [ **編輯**]，然後按一下 [ **顯示詳細資料**]。

5.  在 [ **編輯 Web 服務] 設定**的 **整合式 windows 驗證**中，選取 [ **協商**]、[ **整合式 windows 驗證**] 或 [ **無**]。

6.  根據用戶端的功能和您環境中的支援，選取下列其中一項或多項：
    
      - **啟用 Pin 驗證** ，以允許使用 pin 碼驗證用戶端。
    
      - [**啟用憑證驗證**] 以讓集區中的伺服器對用戶端發出憑證。
    
      - [**啟用憑證鏈下載**] 可讓顯示驗證憑證的伺服器下載該憑證的憑證鏈。

7.  按一下 **[認可]**。

</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 控制台中設定驗證](lync-server-2013-configuring-authentication-in-the-lync-server-control-panel.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

