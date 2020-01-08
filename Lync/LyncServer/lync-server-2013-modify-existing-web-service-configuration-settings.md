---
title: Lync Server 2013：修改現有的 Web 服務設定設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Modify existing Web Service configuration settings
ms:assetid: bd9c7aa5-d31c-4fab-b31d-8baae26b1296
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182580(v=OCS.15)
ms:contentKeyID: 48185272
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f53d0eb34412c746332a0f74d140b6c41c9c257f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982625"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-existing-web-service-configuration-settings-in-lync-server-2013"></a>在 Lync Server 2013 中修改現有的 Web 服務配置設定

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

您可以使用 [ **Web 服務**] 頁面來設定存取 Lync Server 2013 相關 web 伺服器與 web 服務的驗證方法。

請依照這些步驟來修改現有的 Web 服務原則。

<div>

## <a name="to-modify-existing-web-service-configuration-settings"></a>修改現有的 Web 服務設定

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您在其中部署 Lync Server 2013 的網路中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**安全性**]，然後按一下 [ **Web 服務**]。

4.  在 [ **Web 服務**] 頁面上，按一下 [設定]，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**]。

5.  在 [**編輯 Web 服務**] 中，在**整合的 windows 驗證**中，選取 [**協商**]、[**整合式 windows 驗證**] 或 [**無**]。

6.  根據您的環境中用戶端和支援的功能，選取下列一或多個專案：
    
      - **啟用 Pin 驗證**，讓用戶端使用 pin 碼進行驗證。
    
      - **啟用憑證驗證**，將池中的伺服器頒發憑證給用戶端。
    
      - **啟用憑證連結下載**，讓伺服器提供驗證憑證下載該憑證的憑證鏈。

7.  按一下 [認可]****。

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 [控制台] 中設定驗證](lync-server-2013-configuring-authentication-in-the-lync-server-control-panel.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

