---
title: 針對商務用 Skype Online 客戶設定同盟支援
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
localization_priority: Normal
description: '如果您在組織中部署商務用 Skype, 您可以與一個或多個商務用 Skype Online 客戶的網域進行聯盟。 '
ms.openlocfilehash: c6cf36abbbf8876a8aa349d4576b45220517b89e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188791"
---
# <a name="configuring-federation-support-for-a-skype-for-business-online-customer-in-skype-for-business-server"></a>在商務用 Skype Server 中設定商務用 Skype Online 客戶的同盟支援 

您可以透過下列任何一種方式, 為貴組織中的使用者提供通訊服務:

  - 在您的組織中部署商務用 Skype 伺服器 (稱為*內部部署服務*), 並在您的組織中設定商務用 skype 使用者帳戶。
  - 使用主機服務提供者設定 Microsoft 商務用 Skype Online 客戶帳戶, 並設定擁有主機提供者的使用者帳戶 (稱為*線上服務*)。

如果您在組織中部署商務用 Skype, 您可以與一個或多個商務用 Skype Online 客戶的網域進行聯盟。 若要在內部部署商務用 Skype online 與商務用 skype Online 客戶的使用者之間啟用同盟, 您必須設定商務用 Skype Online 客戶的網域和使用者支援。

> [!NOTE]  
> 本檔只說明將貴組織設定為支援與商務用 Skype Online 客戶聯盟的程式。 本檔不說明設定商務用 Skype Online 客戶支援同盟的程式。 

## <a name="prerequisites-for-federating-with-a-skype-for-business-online-customer"></a>與商務用 Skype Online 客戶進行聯盟的先決條件

若要與商務用 Skype Online 客戶進行聯盟, 您應該已完成貴組織中商務用 Skype Server 的初始部署與設定。 這包括下列各項:

  - 在您的組織中部署至少一個標準版伺服器或一個企業版的前端池。 
  - 啟用商務用 Skype Server 的內部使用者帳戶。 
  - 至少部署一個 Edge 伺服器以及支援外部使用者存取所需的其他元件。 如需詳細資訊, 請參閱[管理商務用 Skype Server 的同盟和外部存取](../managing-federation-and-external-access.md)。
  - 在貴組織內啟用同盟支援, 並設定適當的方法來控制聯盟網域的存取。 如需詳細資訊, 請參閱[啟用或停用遠端使用者存取](../access-edge/enable-or-disable-remote-user-access.md)及[管理貴組織的 SIP 聯盟提供者](../sip-providers/manage-sip-federated-providers-for-your-organization.md)。
  - 針對貴組織中的使用者啟用外部使用者存取。 如需詳細資訊, 請參閱[將外部使用者存取原則指派給商務用 Skype 的使用者](../external-access-policies/assign-an-external-user-access-policy.md)。



## <a name="configure-federation-support-for-a-skype-for-business-online-domain"></a>設定商務用 Skype Online 網域的同盟支援

與商務用 Skype Online 客戶進行聯盟時, 必須完成下列步驟:

  - 設定商務用 Skype Online 2010 客戶的網域支援 (例如, contoso.onmicrosoft.com)。 根據在[與商務用 Skype Online 客戶進行聯盟所需的先決條件](#prerequisites-for-federating-with-a-skype-for-business-online-customer), 您應該已經針對貴組織啟用同盟。 啟用同盟時, 必須指定要用來控制聯盟網域存取權的方法。 如果您將組織設定為使用 [探索], 將網域新增到貴組織的 [允許] 清單是選擇性的。 如果您沒有啟用網域探索, 您必須將商務用 Skype Online 客戶的功能變數名稱新增至您的 [允許的網域] 清單。 您可以使用商務用 Skype Server 的 [控制台] 或執行**新的 CSAllowedDomain** Cmdlet 來新增功能變數名稱。 如需使用商務用 Skype Server [控制台] 的詳細資料, 包括啟用網域探索, 請參閱[在商務用 Skype Server 中管理貴組織的 SIP 同盟提供者](../sip-providers/manage-sip-federated-providers-for-your-organization.md)。 如需使用**CSAllowedDomain** Cmdlet 新增網域的詳細資訊, 請參閱[CSAllowedDomain](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsAllowedDomain)。

    > [!NOTE]  
    > 商務用 Skype Online 客戶可以有多個網域。 如果您想要與一個以上的網域聯盟, 您必須針對您要支援同盟的每個個別網域設定支援, 而且商務用 Skype Online 客戶的系統必須針對每個網域啟用同盟, 才能受同盟。

  - 針對您要與其聯盟之商務用 Skype Online 客戶網域的主機提供者設定支援。 使用本節中的程式來設定託管提供者的支援。

    > [!NOTE]  
    > 此步驟僅適用于與商務用 Skype Online 客戶網域進行聯盟, 不適用於與在聯盟夥伴位置上部署之任何網域的同盟。


### <a name="to-configure-support-for-a-hosting-provider"></a>若要設定主機服務提供者的支援

1.  從前端伺服器開始, 啟動商務用 Skype Server 管理命令介面: 按一下 [**開始**], 按一下 [**所有程式**], 按一下 [**商務用 skype**Server], 然後按一下 [**商務用 skype server 管理命令**介面]。

2.  執行**新的 CsHostingProvider** Cmdlet 來建立及設定主機服務提供者。 例如，執行：
    
        New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification -Enabled $True -EnabledSharedAddressSpace $False -HostsOCSUsers $False -IsLocal $False
    
    上述範例會設定下列參數：
    
      - 身分**識別**會為您建立的主機服務提供者指定唯一的字串值識別碼。 請注意，如果已對該 Identity 設定現有提供者，則命令會失敗。
    
      - **ProxyFQDN**指定主機提供者所使用之 proxy 伺服器的完整功能變數名稱 (FQDN)。 您無法修改此值。 如果裝載提供者變更其 Proxy 伺服器，則您必須刪除並重新建立該提供者的項目。
    
      - **VerificationLevel**指定如何驗證從主機託管提供者傳送的訊息 (或 if), 以確保它們已從該提供者傳送。
    
      - **Enabled ** 指出網域與裝載提供者之間的網路連線是否已啟用。只有將此值設為 **True **，才能在兩個組織之間交換訊息。
    
      - **EnabledSharedAddressSpace ** 會指出裝載提供者是否已在共用 SIP 位址空間 (分割網域) 案例中使用。
    
      - **HostsOCSUsers**表示主機服務提供者是否是用來主持商務用 Skype Server 帳戶。 如果為 **False **，則提供者會裝載其他帳戶類型，例如 Microsoft Exchange 帳戶。
    
      - **IsLocal**表示主機服務提供者所使用的 proxy 伺服器是否包含在您的商務用 Skype 伺服器拓撲中。
    
    如需有關使用此 Cmdlet 的詳細資訊, 請參閱[新-CsHostingProvider](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsHostingProvider)。

## <a name="configure-user-access-for-federation-with-a-skype-for-business-online-customer"></a>針對商務用 Skype Online 客戶設定聯盟的使用者存取權 

您必須設定貴組織中所有使用者的使用者帳戶, 才能讓他們與聯盟夥伴進行通訊。 此設定適用于所有聯盟夥伴, 包括您支援同盟的任何 Microsoft 商務用 Skype Online 客戶網域。 如需有關設定使用者帳戶的同盟支援的詳細資料, 請參閱[設定控制聯盟使用者存取權的原則](../external-access-policies/configure-policies-to-control-federated-user-access.md), 以及[將外部使用者存取原則指派給商務用 Skype 的使用者](../external-access-policies/assign-an-external-user-access-policy.md)。

## <a name="verify-communications-with-a-skype-for-business-online-customer-in-skype-for-business-server"></a>在商務用 Skype Server 中驗證與商務用 Skype Online 客戶的通訊

若要讓貴組織中的商務用 Skype 使用者與商務用 Skype Online 客戶的使用者通訊, 您必須已完成下列步驟:

  - 符合所有先決條件。 這包括部署您的內部與邊緣伺服器、啟用貴組織的同盟支援, 以及設定使用者帳戶。 如需詳細資訊, 請參閱[與商務用 Skype Online 客戶進行聯盟的先決條件](#prerequisites-for-federating-with-a-skype-for-business-online-customer)。
  - 在內部部署中設定網域存取支援。 這包括建立主機提供者專案並將您的部署設定為允許從商務用 Skype Online 客戶網域存取。 如需詳細資訊, 請參閱[設定商務用 Skype Online 網域的同盟支援](#configure-federation-support-for-a-skype-for-business-online-domain)。
  - 已將您的使用者帳戶設定為支援同盟。 如需詳細資訊, 請參閱[使用商務用 Skype Online 客戶設定聯盟的使用者存取權](#configure-user-access-for-federation-with-a-skype-for-business-online-customer)。

完成這些步驟後, 商務用 Skype Online 客戶完成所有設定的線上服務, 以支援與貴組織的同盟, 請透過測試通訊貴組織的內部使用者以及商務用 Skype Online 客戶的使用者。 如果通訊失敗, 請使用邊緣伺服器的記錄工具來捕獲記錄和追蹤檔案, 以便對問題進行疑難排解。 
