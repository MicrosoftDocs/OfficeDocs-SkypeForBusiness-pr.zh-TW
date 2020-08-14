---
title: 設定商務用 Skype Online 客戶的同盟支援
ms.reviewer: ''
ms:assetid: e5f7f38d-ede5-4af3-88c2-026e8a78df12
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202193(v=OCS.15)
ms:contentKeyID: 48185669
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: '如果您在組織中部署商務用 Skype，則可以與一或多部商務用 Skype Online 客戶的網域同盟。 '
ms.openlocfilehash: b7488d21463782a978c9a3d6263d9fdfc2e59dd9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037283"
---
# <a name="configuring-federation-support-for-a-skype-for-business-online-customer-in-skype-for-business-server"></a>在商務用 Skype Server 中為商務用 Skype Online 客戶設定同盟支援 

您可以利用下列任何方式，為組織中的使用者提供通訊服務：

  - 在組織中部署商務用 Skype Server (稱為 *內部部署服務*) 和設定組織中的商務用 skype 使用者帳戶。
  - 設定具有裝載提供者的 Microsoft 商務用 Skype Online 客戶帳戶，並設定具有裝載提供者 (稱為 *線上服務*) 的使用者帳戶。

如果您在組織中部署商務用 Skype，則可以與一或多部商務用 Skype Online 客戶的網域同盟。 若要在內部部署商務用 Skype 部署的使用者和商務用 Skype Online 客戶的使用者之間啟用同盟，您必須為網域和商務用 Skype Online 客戶的使用者設定支援。

> [!NOTE]  
> 本檔只說明設定您的組織支援與商務用 Skype Online 客戶同盟的程式。 本檔不會說明設定商務用 Skype Online 客戶以支援同盟的程式。 

## <a name="prerequisites-for-federating-with-a-skype-for-business-online-customer"></a>與商務用 Skype Online 客戶進行同盟的必要條件

若要與商務用 Skype Online 客戶同盟，您應該已經完成您組織中商務用 Skype Server 的初始部署和設定。 其中包括下列項目：

  - 在您的組織中部署至少一部 Standard Edition server 或單一 Enterprise Edition 前端集區。 
  - 為商務用 Skype Server 啟用內部使用者帳戶。 
  - 部署至少一部 Edge Server，以及支援外部使用者存取所需的其他元件。 如需詳細資訊，請參閱 [管理同盟和外部存取商務用 Skype Server](../managing-federation-and-external-access.md)。
  - 在組織內啟用同盟支援，並設定適當的方法來控制同盟網域的存取。 如需詳細資訊，請參閱 [啟用或停用組織的遠端使用者存取](../access-edge/enable-or-disable-remote-user-access.md) 和 [管理 SIP 同盟提供者](../sip-providers/manage-sip-federated-providers-for-your-organization.md)。
  - 為組織中的使用者啟用外部使用者存取。 如需詳細資訊，請參閱 [將外部使用者存取原則指派給啟用商務用 Skype 的使用者](../external-access-policies/assign-an-external-user-access-policy.md)。



## <a name="configure-federation-support-for-a-skype-for-business-online-domain"></a>設定商務用 Skype Online 網域的同盟支援

若要與商務用 Skype Online 客戶同盟，您必須完成下列步驟：

  - 為商務用 Skype Online 2010 客戶 (網域設定支援（例如，contoso.onmicrosoft.com) ）。 如在 [與商務用 Skype Online 客戶進行同盟的必要條件](#prerequisites-for-federating-with-a-skype-for-business-online-customer)中所指定，您應該已經為組織啟用同盟。 啟用同盟需要指定同盟網域用來控制存取的方法。 如果您將組織設定成使用探索，則可選擇是否將網域新增至組織的允許清單中。 如果您未啟用網域探索，您必須將商務用 Skype Online 客戶的功能變數名稱新增至您的允許的網域清單。 您可以使用商務用 Skype Server 控制台或執行 **CSAllowedDomain** Cmdlet，新增功能變數名稱。 如需使用商務用 Skype Server 控制台（包括啟用網域探索）的詳細資訊，請參閱 [在商務用 Skype Server 中管理組織的 SIP 同盟提供者](../sip-providers/manage-sip-federated-providers-for-your-organization.md)。 如需使用 **CSAllowedDomain** Cmdlet 新增網域的詳細資訊，請參閱 [New-CsAllowedDomain](https://docs.microsoft.com/powershell/module/skype/New-CsAllowedDomain)。

    > [!NOTE]  
    > 商務用 Skype Online 客戶可以有多個網域。 如果您想要與一個以上的網域同盟，您必須為想要支援同盟的各個個別網域設定支援，並且商務用 Skype Online 客戶的系統管理員必須針對每個要同盟的網域啟用同盟。

  - 針對您要與其同盟的商務用 Skype Online 客戶網域，設定支援的主機供應商。 請使用本節中的程序，為裝載提供者設定相關支援。

    > [!NOTE]  
    > 此步驟僅適用于與商務用 Skype Online 客戶網域的同盟，而不是與同盟協力廠商所在位置上部署的任何網域的同盟。


### <a name="to-configure-support-for-a-hosting-provider"></a>針對裝載提供者設定支援

1.  從前端伺服器啟動商務用 Skype Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **商務用 skype 伺服器**]，然後按一下 [ **商務用 skype server 管理命令**介面]。

2.  執行 **New-CsHostingProvider** Cmdlet，以建立和設定裝載提供者。 例如，執行：
    
        New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification -Enabled $True -EnabledSharedAddressSpace $False -HostsOCSUsers $False -IsLocal $False
    
    上述範例會設定下列參數：
    
      - **Identity** 會為您建立的裝載提供者指定唯一字串值識別碼。請注意，如果已對該 Identity 設定現有提供者，則命令會失敗。
    
      - **ProxyFQDN** 會指定裝載提供者所使用 Proxy 伺服器的完整網域名稱 (FQDN)。您無法修改此值。如果裝載提供者變更其 Proxy 伺服器，則您必須刪除並重新建立該提供者的項目。
    
      - **VerificationLevel** 會指定如何驗證 (或是否驗證) 從裝載提供者傳送的訊息，以確認它們確實是傳送自該提供者。
    
      - **Enabled** 會指出網域和裝載提供者之間的網路連線是否已啟用。只有將此值設為 **True**，才能在兩個組織之間交換訊息。
    
      - **EnabledSharedAddressSpace** 會指出裝載提供者是否已在共用 SIP 位址空間 (分割網域) 案例中使用。
    
      - **HostsOCSUsers** 會指出裝載提供者是否是用來主控商務用 Skype 伺服器帳戶。 若 **為 False**，則提供者會主控其他帳戶類型，例如 Microsoft Exchange 帳戶。
    
      - **IsLocal** 會指出裝載提供者所使用的 proxy 伺服器是否包含在商務用 Skype 伺服器拓撲中。
    
    如需使用此 Cmdlet 的詳細資訊，請參閱 [New-CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/New-CsHostingProvider)。

## <a name="configure-user-access-for-federation-with-a-skype-for-business-online-customer"></a>使用商務用 Skype Online 客戶設定同盟的使用者存取 

您必須將組織中所有使用者的使用者帳戶設定成允許與同盟協力廠商通訊。 此設定適用于所有同盟協力廠商，包括您用來支援同盟的任何 Microsoft 商務用 Skype Online 客戶網域。 如需設定使用者帳戶同盟支援的詳細資訊，請參閱 [設定原則以控制同盟使用者存取](../external-access-policies/configure-policies-to-control-federated-user-access.md) ，以及 [將外部使用者存取原則指派給啟用商務用 Skype 的使用者](../external-access-policies/assign-an-external-user-access-policy.md)。

## <a name="verify-communications-with-a-skype-for-business-online-customer-in-skype-for-business-server"></a>在商務用 Skype Server 中驗證與商務用 Skype Online 客戶的通訊

若要讓組織中的商務用 Skype 使用者能夠與商務用 Skype Online 客戶的使用者進行通訊，您必須完成下列步驟：

  - 符合所有必要條件。 這包括部署您的內部及 edge 伺服器、啟用組織的同盟支援和設定使用者帳戶。 如需詳細資訊，請參閱 [與商務用 Skype Online 客戶聯盟的必要條件](#prerequisites-for-federating-with-a-skype-for-business-online-customer)。
  - 設定內部部署中的網域存取支援。 這包括建立主機提供者專案和設定您的部署，以允許從商務用 Skype Online 客戶的網域進行存取。 如需詳細資訊，請參閱 [Configure 商務用 Skype Online 網域的同盟支援](#configure-federation-support-for-a-skype-for-business-online-domain)。
  - 設定您的使用者帳戶以支援同盟。 如需詳細資訊，請參閱 [使用商務用 Skype Online 客戶設定同盟的使用者存取](#configure-user-access-for-federation-with-a-skype-for-business-online-customer)。

完成所有這些步驟之後，商務用 Skype Online 客戶的系統管理員完成所有設定其線上服務以支援與組織的同盟，請測試組織內部使用者與商務用 Skype Online 客戶之間的通訊，以驗證通訊。 如果通訊不成功，請使用 Edge Server 中的記錄工具來捕獲記錄檔和追蹤檔，以便疑難排解問題。 
