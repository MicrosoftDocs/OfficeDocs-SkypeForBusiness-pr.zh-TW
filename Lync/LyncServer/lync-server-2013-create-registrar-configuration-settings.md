---
title: Lync Server 2013：建立註冊機配置設定
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
ms.openlocfilehash: bf2f9eac959e9061e42bdc05982593c9f21aa2b0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200179"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-registrar-configuration-settings-in-lync-server-2013"></a>在 Lync Server 2013 中建立註冊機配置設定

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-03-17_

您可以使用註冊機構來設定 proxy 伺服器驗證方法。 您指定的驗證通訊協定會決定集區中的伺服器在用戶端上面臨的挑戰類型。 可用的通訊協定包括：

  - **Kerberos**    這是可供用戶端使用的最強式密碼型驗證配置，但通常只適用于企業用戶端，因為它需要用戶端連線至金鑰發佈中心 (Kerberos 網域控制站) 。 此設定適用于伺服器只驗證企業用戶端的情況。

  - **NTLM**    這是以密碼為基礎的驗證，可供在密碼上使用挑戰回應雜湊配置的用戶端使用。 這是唯一可供用戶端使用的驗證表單，但不連接到金鑰發佈中心 (Kerberos 網域控制站) （例如遠端使用者）。 如果伺服器只驗證遠端使用者，您應該選擇 [NTLM]。

  - **憑證驗證**    當伺服器需要從 Lync Phone Edition 用戶端、公共區域電話、Lync 2013 和 Lync Windows Store 應用程式取得憑證時，這是一種新的驗證方法。 在 Lync Phone Edition 用戶端上，使用者登入並透過提供個人識別碼 (PIN) 來成功驗證之後，Lync Server 2013 接著會布建 SIP URI 至電話，並布建 Lync Server 簽署憑證或識別 Joe (Ex： SN=joe@contoso.com ) 至電話的使用者憑證。 此憑證用來驗證註冊機構和 Web 服務。

<div>


> [!NOTE]  
> 當伺服器同時支援遠端和企業用戶端的驗證時，建議您啟用 Kerberos 和 NTLM。 Edge Server 和內部伺服器會進行通訊，以確保只會向遠端用戶端提供 NTLM 驗證。 如果這些伺服器上只啟用 Kerberos，則無法驗證遠端使用者。 如果企業使用者也會驗證服務器，則會使用 Kerberos。<BR>如果您要使用 Lync Windows Store 應用程式用戶端，則必須啟用憑證驗證。



</div>

請遵循下列步驟建立新的註冊機。

<div>

## <a name="to-create-new-registrar-configuration-settings"></a>若要建立新的註冊機配置設定

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您已部署 Lync Server 2013 之網路中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱[Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中，按一下 [**安全性**]，然後按一下 [**註冊**]。

4.  在 [**註冊機**] 頁面上，按一下 [**新增**]

5.  在 [**選取服務**] 中，按一下要套用註冊器的服務，然後按一下 **[確定]**。

6.  在 [**新註冊機] 設定**中，根據用戶端的功能和您環境中的支援，選取下列其中一項或多項：
    
      - **啟用 kerberos 驗證**讓集區中的伺服器使用 Kerberos 驗證，提出挑戰。
    
      - **啟用 ntlm 驗證**讓集區中的伺服器使用 NTLM 時面臨挑戰。
    
      - [**啟用憑證驗證**] 以讓集區中的伺服器對用戶端發出憑證。

7.  按一下 **[認可]**。

</div>

</div>

<span> </span>

</div>

</div>

</div>

