---
title: Lync Server 2013： 設定 Lync Online 網域同盟支援
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
ms.openlocfilehash: e1f8a73451f88b5195a5137013082dad2c8d5b14
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140336"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-federation-support-for-a-lync-online-domain-in-lync-server-2013"></a>在 Lync Server 2013 中設定 Lync Online 網域同盟支援

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-11-01_

與 Microsoft Lync Online 2010 客戶同盟需要完成下列步驟：

  - 設定 Lync Online 2010 customer (例如，contoso.onmicrosoft.com) 的網域的支援。 指定此文件[與 Lync Server 2013 中的 Lync Online 客戶同盟的先決條件](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md)區段中，您應該已為您的組織啟用同盟。 啟用同盟需要指定同盟網域用來控制存取的方法。 如果您將組織設定成使用探索，則可選擇是否將網域新增至組織的允許清單中。 如果您未啟用網域探索，您必須將 Lync Online 客戶的網域名稱新增至允許的網域清單。 使用 Lync Server Control Panel，或執行**New-csalloweddomain**指令程式，您可以新增的網域名稱。 如需使用 Lync Server Control Panel，包括啟用探索的網域，請參閱作業文件中的[管理 SIP 同盟提供者在 Lync Server 2013 組織](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)。 如需使用**New-csalloweddomain**指令程式來新增網域的詳細資訊，請參閱作業文件中的[New-csalloweddomain](https://docs.microsoft.com/powershell/module/skype/New-CsAllowedDomain) 。
    
    <div>
    

    > [!NOTE]  
    > Lync Online 客戶可以有多個網域。 如果您想要同盟與一個以上的網域，您必須設定為每個個別的網域與您想要支援同盟，以及 Lync Online 客戶的系統管理員必須啟用每個為同盟網域同盟的支援。

    
    </div>

  - 設定您想要同盟的 Lync Online 2010 客戶網域的裝載提供者的支援。 請使用本節中的程序，為裝載提供者設定相關支援。
    
    <div>
    

    > [!NOTE]  
    > 僅適用於與網域同盟的 Lync Online 客戶，則不是內部部署同盟的協力廠商位置任何網域同盟時才需要此步驟。

    
    </div>

<div>

## <a name="to-configure-support-for-a-hosting-provider"></a>針對裝載提供者設定支援

1.  從前端伺服器上，啟動 [Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。

2.  執行 **New-CsHostingProvider** Cmdlet，以建立和設定裝載提供者。 例如，執行：
    
        New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification -Enabled $True -EnabledSharedAddressSpace $False -HostsOCSUsers $False -IsLocal $False
    
    上述範例會設定下列參數：
    
      - **Identity** 會為您建立的裝載提供者指定唯一字串值識別碼。請注意，如果已對該 Identity 設定現有提供者，則命令會失敗。
    
      - **ProxyFQDN** 會指定裝載提供者所使用 Proxy 伺服器的完整網域名稱 (FQDN)。您無法修改此值。如果裝載提供者變更其 Proxy 伺服器，則您必須刪除並重新建立該提供者的項目。
    
      - **VerificationLevel** 會指定如何驗證 (或是否驗證) 從裝載提供者傳送的訊息，以確認它們確實是傳送自該提供者。
    
      - **Enabled** 會指出網域和裝載提供者之間的網路連線是否已啟用。只有將此值設為 **True**，才能在兩個組織之間交換訊息。
    
      - **EnabledSharedAddressSpace** 會指出裝載提供者是否已在共用 SIP 位址空間 (分割網域) 案例中使用。
    
      - **HostsOCSUsers**指出裝載提供者是否用來裝載 Lync Server 帳戶。 如果**為 False**，提供者主控其他帳戶類型，例如 Microsoft Exchange 帳戶。
    
      - **IsLocal**指出裝載提供者所使用的 proxy 伺服器是否包含在您的 Lync Server 拓撲內。
    
    如需有關使用此 cmdlet 的詳細資訊，請參閱作業文件中的[New-cshostingprovider](https://docs.microsoft.com/powershell/module/skype/New-CsHostingProvider) 。

</div>

</div>

<span> </span>

</div>

</div>

</div>

