---
title: Lync Server 2013：修改現有的註冊器設定設定
description: Lync Server 2013：修改現有的註冊機設定。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify existing Registrar configuration settings
ms:assetid: a8931511-3e66-49ed-a3ec-03bcd61ce1f0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182566(v=OCS.15)
ms:contentKeyID: 48185095
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a4a58a73ec67a320a9d9ee9a29b8e0a4708aa40a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565899"
---
# <a name="modify-existing-registrar-configuration-settings-in-lync-server-2013"></a>在 Lync Server 2013 中修改現有的註冊器設定設定

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

您可以使用註冊機構來設定 proxy 伺服器驗證通訊協定。 如需可用的通訊協定資訊，請參閱 [在 Lync Server 2013 中建立註冊器設定設定](lync-server-2013-create-registrar-configuration-settings.md)。

<div>


> [!NOTE]  
> 當伺服器同時支援遠端和企業用戶端的驗證時，建議您啟用 Kerberos 和 NTLM。 Edge Server 和內部伺服器會進行通訊，以確保只會向遠端用戶端提供 NTLM 驗證。 如果這些伺服器上只啟用 Kerberos，則無法驗證遠端使用者。 如果企業使用者也會驗證服務器，則會使用 Kerberos。



</div>

請遵循下列步驟來修改現有的註冊機。

<div>

## <a name="to-modify-existing-registrar-configuration-settings"></a>若要修改現有的註冊器配置設定

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您已部署 Lync Server 2013 之網路中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中，按一下 [ **安全性** ]，然後按一下 [ **註冊**]。

4.  在 [ **註冊機構** ] 頁面上，按一下服務，然後按一下 [ **編輯**]，再按一下 [ **顯示詳細資料**]。

5.  在 [ **編輯註冊機設定**] 中，依據用戶端的功能和您環境中的支援，選取下列其中一項或多項：
    
      - **啟用 kerberos 驗證** 讓集區中的伺服器使用 Kerberos 驗證，提出挑戰。
    
      - **啟用 ntlm 驗證** 讓集區中的伺服器使用 NTLM 時面臨挑戰。
    
      - [**啟用憑證驗證**] 以讓集區中的伺服器對用戶端發出憑證。

6.  按一下 **[認可]**。

</div>

</div>

<span> </span>

</div>

</div>

</div>

