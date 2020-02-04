---
title: Lync Server 2013：針對 Lync Online 網域設定同盟支援
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure federation support for a Lync Online domain
ms:assetid: 19d5d5be-cd7f-47b8-b6c5-651a3191def7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202166(v=OCS.15)
ms:contentKeyID: 48183530
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9f883e8d730e63788b4cbe0ccd3315f21e6fea97
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726593"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-federation-support-for-a-lync-online-domain-in-lync-server-2013"></a>在 Lync Server 2013 中設定 Lync Online 網域的同盟支援

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

使用 Microsoft Lync Online 2010 客戶進行聯盟，必須完成下列步驟：

  - 針對 Lync Online 2010 客戶的網域設定支援（例如，contoso.onmicrosoft.com）。 根據在本檔的[Lync Server 2013 區段中與 Lync Online 客戶進行聯盟的先決條件](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md)，您應該已經針對您的組織啟用同盟。 啟用同盟時，必須指定要用來控制聯盟網域存取權的方法。 如果您將組織設定為使用 [探索]，將網域新增到貴組織的 [允許] 清單是選擇性的。 如果您沒有啟用網域探索，您必須將 Lync Online 客戶的功能變數名稱新增至 [允許的網域] 清單。 您可以使用 Lync Server [控制台] 或執行**新的 CSAllowedDomain** Cmdlet 來新增功能變數名稱。 如需使用 Lync Server [控制台] 的詳細資料，包括啟用網域探索，請參閱在作業檔中[管理您的組織在 Lync Server 2013 中的 SIP 同盟提供者](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)。 如需使用**CSAllowedDomain** Cmdlet 來新增網域的詳細資料，請參閱 [作業] 檔中的 [[新增-CSAllowedDomain](https://docs.microsoft.com/powershell/module/skype/New-CsAllowedDomain) ]。
    
    <div>
    

    > [!NOTE]  
    > Lync Online 客戶可以有多個網域。 如果您想要與一個以上的網域聯盟，您必須針對每一個您要支援同盟的網域設定支援，而且 Lync Online 客戶的管理員必須針對每一個要進行聯盟的網域啟用同盟。

    
    </div>

  - 針對您要與其聯盟的 Lync Online 2010 客戶網域，設定其主機服務提供者支援。 使用本節中的程式來設定託管提供者的支援。
    
    <div>
    

    > [!NOTE]  
    > 此步驟僅適用于具備 Lync Online 客戶網域的同盟，不適用於與在聯盟夥伴位置上部署之任何網域的同盟。

    
    </div>

<div>

## <a name="to-configure-support-for-a-hosting-provider"></a>若要設定主機服務提供者的支援

1.  從前端伺服器，啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  執行**新的 CsHostingProvider** Cmdlet 來建立及設定主機服務提供者。 例如，執行：
    
        New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification -Enabled $True -EnabledSharedAddressSpace $False -HostsOCSUsers $False -IsLocal $False
    
    上述範例會設定下列參數：
    
      - 身分**識別**會為您建立的主機服務提供者指定唯一的字串值識別碼。 請注意，如果已對該 Identity 設定現有提供者，則命令會失敗。
    
      - **ProxyFQDN**指定主機提供者所使用之 proxy 伺服器的完整功能變數名稱（FQDN）。 您無法修改此值。 如果裝載提供者變更其 Proxy 伺服器，則您必須刪除並重新建立該提供者的項目。
    
      - **VerificationLevel**指定如何驗證從主機託管提供者傳送的訊息（或 if），以確保它們已從該提供者傳送。
    
      - **Enabled ** 指出網域與裝載提供者之間的網路連線是否已啟用。只有將此值設為 **True **，才能在兩個組織之間交換訊息。
    
      - **EnabledSharedAddressSpace ** 會指出裝載提供者是否已在共用 SIP 位址空間 (分割網域) 案例中使用。
    
      - **HostsOCSUsers**表示主機服務提供者是否用來託管 Lync Server 帳戶。 如果為 **False **，則提供者會裝載其他帳戶類型，例如 Microsoft Exchange 帳戶。
    
      - **IsLocal** ：指示主機服務提供者所使用的 proxy 伺服器是否包含在您的 Lync server 拓撲中。
    
    如需有關使用此 Cmdlet 的詳細資訊，請參閱作業檔中的[新 CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/New-CsHostingProvider) 。

</div>

</div>

<span> </span>

</div>

</div>

</div>

