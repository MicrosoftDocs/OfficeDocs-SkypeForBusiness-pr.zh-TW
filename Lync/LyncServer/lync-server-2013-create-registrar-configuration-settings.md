---
title: Lync Server 2013：建立註冊機構配置設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create Registrar configuration settings
ms:assetid: eddfbdd2-cfd0-4c03-986e-443d6728db7d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182601(v=OCS.15)
ms:contentKeyID: 48185758
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 81aec9ee6923dc125769ad16a26390b23155852c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763467"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-registrar-configuration-settings-in-lync-server-2013"></a>在 Lync Server 2013 中建立註冊機構配置設定

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-03-17_

您可以使用註冊機構來設定 proxy 伺服器驗證方法。 您指定的驗證通訊協定決定了將池中的伺服器問題到用戶端所面臨的挑戰類型。 可用的通訊協定包括：

  - **Kerberos**   這是用戶端可用的最強式密碼驗證配置，但通常只有企業用戶端才能使用，因為它需要用戶端連線到金鑰發佈中心（Kerberos 網網域控制站）。 此設定適用于伺服器只驗證企業用戶端的情況。

  - **NTLM**   這是在密碼上使用質詢回應雜湊配置的用戶端提供的密碼式驗證。 這是不需連線到金鑰發佈中心（Kerberos 網網域控制站）（例如遠端使用者）的用戶端可使用的唯一驗證形式。 如果伺服器只驗證遠端使用者，您應該選擇 [NTLM]。

  - **憑證驗證**   當伺服器需要從 Lync Phone Edition 用戶端、常用的區域手機、lync 2013 和 lync Windows Store 應用程式取得憑證時，這是新的驗證方法。 在 Lync Phone Edition 用戶端上，使用者登入並透過提供個人識別碼（PIN）來成功驗證之後，Lync Server 2013 接著將 SIP URI 提供給手機，並將識別 Joe （Ex： SN=joe@contoso.com）的使用者憑證提供給手機。 這個憑證是用來向註冊機構和 Web 服務進行驗證。

<div>


> [!NOTE]  
> 我們建議您在伺服器同時支援遠端與企業用戶端的驗證時，同時啟用 Kerberos 和 NTLM。 邊緣伺服器與內部伺服器通訊，以確保只提供 NTLM 驗證給遠端用戶端。 如果在這些伺服器上只啟用 Kerberos，就無法驗證遠端使用者。 如果企業使用者也要針對伺服器進行驗證，則會使用 Kerberos。<BR>如果您要使用 Lync Windows Store app 用戶端，您必須啟用憑證驗證。



</div>

請依照這些步驟來建立新的註冊機構。

<div>

## <a name="to-create-new-registrar-configuration-settings"></a>建立新的註冊機構配置設定

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您在其中部署 Lync Server 2013 的網路中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**安全性**]，然後按一下 [**註冊機**]。

4.  在 [**註冊機**] 頁面上，按一下 [**新增**]

5.  在 [**選取服務**] 中，按一下要套用註冊機構的服務，然後按一下 **[確定]**。

6.  在 [**新的註冊機構設定**] 中，根據您的環境中用戶端和支援的功能，選取下列一或多個專案：
    
      - 使用 Kerberos 驗證來**啟用 kerberos 驗證**，讓伺服器在池中有問題的挑戰。
    
      - **啟用 ntlm 驗證**，以讓池中的伺服器面臨使用 NTLM 的問題。
    
      - **啟用憑證驗證**，將池中的伺服器頒發憑證給用戶端。

7.  按一下 [認可]****。

</div>

</div>

<span> </span>

</div>

</div>

</div>

