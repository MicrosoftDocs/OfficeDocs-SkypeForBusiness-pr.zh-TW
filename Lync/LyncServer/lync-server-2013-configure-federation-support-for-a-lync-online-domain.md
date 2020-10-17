---
title: Lync Server 2013：設定 Lync Online 網域的同盟支援
description: Lync Server 2013：設定 Lync Online 網域的同盟支援。
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
ms.openlocfilehash: ee814efdfb68d3c5ef9772b733bf136ae53ea9e2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553299"
---
# <a name="configure-federation-support-for-a-lync-online-domain-in-lync-server-2013"></a>在 Lync Server 2013 中設定 Lync Online 網域的同盟支援

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

與 Microsoft Lync Online 2010 客戶同盟需要您完成下列步驟：

  - 為 Lync Online 2010 客戶 (的網域設定支援，例如，contoso.onmicrosoft.com) 。 如您在本檔的 [與 lync Online 客戶進行同盟的 [必要條件2013中](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md) 所指定，您應該已經為您的組織啟用同盟。 啟用同盟需要指定同盟網域用來控制存取的方法。 如果您將組織設定成使用探索，則可選擇是否將網域新增至組織的允許清單中。 如果您未啟用網域探索，您必須將 Lync Online 客戶的功能變數名稱新增至您的允許網域清單。 您可以使用 Lync Server 控制台或執行 **CSAllowedDomain** Cmdlet 來新增功能變數名稱。 如需使用 Lync Server 控制台（包括啟用網域探索）的詳細資訊，請參閱 Operations 檔中的 [管理您組織的 SIP 同盟提供者（Lync server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md) ）。 如需使用 **CSAllowedDomain** Cmdlet 新增網域的詳細資訊，請參閱 Operations 檔中的 [New-CsAllowedDomain](https://docs.microsoft.com/powershell/module/skype/New-CsAllowedDomain) 。
    
    <div>
    

    > [!NOTE]  
    > Lync Online 客戶可以有多個網域。 如果您想要與一個以上的網域同盟，您必須為想要支援同盟的各個個別網域設定支援，並且 Lync Online 客戶的系統管理員必須啟用每個網域的同盟。

    
    </div>

  - 針對您要與其同盟的 Lync Online 2010 客戶網域，設定支援的主機提供者。 請使用本節中的程序，為裝載提供者設定相關支援。
    
    <div>
    

    > [!NOTE]  
    > 此步驟僅適用于與 Lync Online 客戶網域的同盟，而不是用於同盟協力廠商所在位置之任何部署于內部部署的網域的同盟。

    
    </div>

<div>

## <a name="to-configure-support-for-a-hosting-provider"></a>針對裝載提供者設定支援

1.  在前端伺服器上，啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  執行 **New-CsHostingProvider** Cmdlet，以建立和設定裝載提供者。 例如，執行：
    
        New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification -Enabled $True -EnabledSharedAddressSpace $False -HostsOCSUsers $False -IsLocal $False
    
    上述範例會設定下列參數：
    
      - **Identity** 會為您建立的裝載提供者指定唯一字串值識別碼。請注意，如果已對該 Identity 設定現有提供者，則命令會失敗。
    
      - **ProxyFQDN** 會指定裝載提供者所使用 Proxy 伺服器的完整網域名稱 (FQDN)。您無法修改此值。如果裝載提供者變更其 Proxy 伺服器，則您必須刪除並重新建立該提供者的項目。
    
      - **VerificationLevel** 會指定如何驗證 (或是否驗證) 從裝載提供者傳送的訊息，以確認它們確實是傳送自該提供者。
    
      - **Enabled** 會指出網域和裝載提供者之間的網路連線是否已啟用。只有將此值設為 **True**，才能在兩個組織之間交換訊息。
    
      - **EnabledSharedAddressSpace** 會指出裝載提供者是否已在共用 SIP 位址空間 (分割網域) 案例中使用。
    
      - **HostsOCSUsers** 會指出裝載提供者是否是用來裝載 Lync Server 帳戶。 若 **為 False**，則提供者會主控其他帳戶類型，例如 Microsoft Exchange 帳戶。
    
      - **IsLocal** 指出主控提供者所使用的 proxy 伺服器是否包含在 Lync server 拓撲中。
    
    如需使用此 Cmdlet 的詳細資訊，請參閱 Operations 檔中的 [New-CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/New-CsHostingProvider) 。

</div>

</div>

<span> </span>

</div>

</div>

</div>

