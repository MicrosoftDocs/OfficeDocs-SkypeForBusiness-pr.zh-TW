---
title: 設定商務用 Skype Online 客戶的同盟支援
ms.reviewer: ''
ms:assetid: e5f7f38d-ede5-4af3-88c2-026e8a78df12
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202193(v=OCS.15)
ms:contentKeyID: 48185669
mtps_version: v=OCS.15
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: '如果您在組織中部署商務用 Skype，您可以與一或多個 商務用 Skype Online 客戶的網域同盟。 '
ms.openlocfilehash: d180de014c0a7479eb5dc7a6fb60e00e5b136f24
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/25/2022
ms.locfileid: "65676225"
---
# <a name="configuring-federation-support-for-a-skype-for-business-online-customer-in-skype-for-business-server"></a>在 商務用 Skype Server 中設定 商務用 Skype Online 客戶的同盟支援

您可以使用下列任何一種方式，為組織中的使用者提供通訊服務：

- 在組織中部署商務用 Skype Server (稱為內部部署 *服務*) ，並在組織中設定商務用 Skype使用者帳戶。
- 使用主機提供者設定 Microsoft 商務用 Skype Online 客戶帳戶，並使用稱為 線上服務) 的主機提供者 *(* 設定使用者帳戶。

如果您在組織中部署商務用 Skype，您可以與一或多個 商務用 Skype Online 客戶的網域同盟。 若要在內部部署商務用 Skype使用者與 商務用 Skype Online 客戶的使用者之間啟用同盟，您必須設定對 商務用 Skype Online 客戶網域和使用者的支援。

[!INCLUDE [sfbo-retirement-skype](../../../../Hub/includes/sfbo-retirement.md)]

> [!NOTE]  
> 本檔僅說明設定貴組織以支援與 商務用 Skype Online 客戶同盟的程式。 本檔不會說明設定 商務用 Skype Online 客戶以支援同盟的程式。

## <a name="prerequisites-for-federating-with-a-skype-for-business-online-customer"></a>與 商務用 Skype Online 客戶同盟的必要條件

若要與 商務用 Skype Online 客戶同盟，您應該已完成組織中商務用 Skype Server的初始部署和設定。 其中包括下列項目：

- 在組織中部署至少一個Standard Edition伺服器或一個Enterprise Edition前端集區。
- 啟用商務用 Skype Server的內部使用者帳戶。
- 部署至少一個 Edge Server 和其他支援外部使用者存取所需的元件。 如需詳細資訊，請[參閱管理同盟和外部存取商務用 Skype Server](../managing-federation-and-external-access.md)。
- 在您的組織內啟用同盟支援，並設定適當的方法來控制同盟網域的存取權。 如需詳細資訊，請參閱 [啟用或停用遠端使用者存取](../access-edge/enable-or-disable-remote-user-access.md) 和 [管理組織的 SIP 同盟提供者](../sip-providers/manage-sip-federated-providers-for-your-organization.md)。
- 為組織中的使用者啟用外部使用者存取。 如需詳細資訊，[請參閱將外部使用者存取原則指派給已啟用商務用 Skype使用者](../external-access-policies/assign-an-external-user-access-policy.md)。

## <a name="configure-federation-support-for-a-skype-for-business-online-domain"></a>設定 商務用 Skype Online 網域的同盟支援

與 商務用 Skype Online 客戶同盟需要您完成下列步驟：

- 設定對 商務用 Skype Online 2010 客戶 (網域的支援，例如 contoso.onmicrosoft.com) 。 如[與 商務用 Skype Online 客戶](#prerequisites-for-federating-with-a-skype-for-business-online-customer)同盟的必要條件中所指定，您應該已為組織啟用同盟。 啟用同盟需要指定同盟網域用來控制存取的方法。 如果您將組織設定成使用探索，則可選擇是否將網域新增至組織的允許清單中。 如果您未啟用網域探索，則必須將 商務用 Skype Online 客戶的功能變數名稱新增至您允許的網域清單。 您可以使用 商務用 Skype Server 主控台 或執行 **New-CSAllowedDomain** Cmdlet 來新增功能變數名稱。 如需使用商務用 Skype Server 主控台的詳細資訊，包括啟用網域探索，請參閱[在 商務用 Skype Server 中管理貴組織的 SIP 同盟提供者](../sip-providers/manage-sip-federated-providers-for-your-organization.md)。 如需使用 **New-CSAllowedDomain** Cmdlet 新增網域的詳細資訊，請參閱 [New-CsAllowedDomain](/powershell/module/skype/New-CsAllowedDomain)。

  > [!NOTE]  
  > 商務用 Skype Online 客戶可以有多個網域。 如果您想要與多個網域同盟，則必須為您想要支援同盟的每個個別網域設定支援，而 商務用 Skype Online 客戶的系統管理員必須為每個要同盟的網域啟用同盟。

- 設定您要同盟之 商務用 Skype Online 客戶網域的主機提供者支援。 請使用本節中的程序，為裝載提供者設定相關支援。

  > [!NOTE]  
  > 此步驟僅適用于與 商務用 Skype Online 客戶的網域同盟，而非與任何部署在同盟合作夥伴位置的內部部署網域同盟。

### <a name="to-configure-support-for-a-hosting-provider"></a>針對裝載提供者設定支援

1. 從前端伺服器啟動商務用 Skype Server管理命令介面：按一下 [**開始**]，按一下 [**所有程式]**，按一下 **[商務用 Skype Server**]，然後按一下 **[商務用 Skype Server 管理命令介面]**。

2. 執行 **New-CsHostingProvider** Cmdlet，以建立和設定裝載提供者。 例如，執行：

    ```powershell
    New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification -Enabled $True -EnabledSharedAddressSpace $False -HostsOCSUsers $False -IsLocal $False
    ```

    上述範例會設定下列參數：

    - **Identity** 會為您建立的裝載提供者指定唯一字串值識別碼。請注意，如果已對該 Identity 設定現有提供者，則命令會失敗。

    - **ProxyFQDN** 會指定裝載提供者所使用 Proxy 伺服器的完整網域名稱 (FQDN)。您無法修改此值。如果裝載提供者變更其 Proxy 伺服器，則您必須刪除並重新建立該提供者的項目。

    - **VerificationLevel** 會指定如何驗證 (或是否驗證) 從裝載提供者傳送的訊息，以確認它們確實是傳送自該提供者。

    - **Enabled** 會指出網域和裝載提供者之間的網路連線是否已啟用。只有將此值設為 **True**，才能在兩個組織之間交換訊息。

    - **EnabledSharedAddressSpace** 會指出裝載提供者是否已在共用 SIP 位址空間 (分割網域) 案例中使用。

    - **HostsOCSUsers** 指出主機提供者是否用來裝載商務用 Skype Server帳戶。 如果 **為 False**，則提供者會裝載其他帳戶類型，例如 Microsoft Exchange 帳戶。

    - **IsLocal** 指出裝載提供者所使用的 Proxy 伺服器是否包含在您的商務用 Skype Server拓撲中。

    如需使用此 Cmdlet 的詳細資訊，請參閱 [New-CsHostingProvider](/powershell/module/skype/New-CsHostingProvider)。

## <a name="configure-user-access-for-federation-with-a-skype-for-business-online-customer"></a>設定與 商務用 Skype Online 客戶同盟的使用者存取權

您必須將組織中所有使用者的使用者帳戶設定成允許與同盟協力廠商通訊。 此設定適用于所有同盟合作夥伴，包括您支援同盟的任何 Microsoft 商務用 Skype Online 客戶網域。 如需設定使用者帳戶同盟支援的詳細資訊，請參閱設定原則[以控制同盟使用者存取](../external-access-policies/configure-policies-to-control-federated-user-access.md)和[將外部使用者存取原則指派給已啟用商務用 Skype使用者](../external-access-policies/assign-an-external-user-access-policy.md)。

## <a name="verify-communications-with-a-skype-for-business-online-customer-in-skype-for-business-server"></a>在 商務用 Skype Server 中確認與 商務用 Skype Online 客戶的通訊

若要讓組織中的商務用 Skype使用者與商務用 Skype Online 客戶的使用者通訊，您必須已完成下列步驟：

- 符合所有必要條件。 這包括部署內部和邊緣伺服器、為您的組織啟用同盟支援，以及設定使用者帳戶。 如需詳細資訊，請參閱[與 商務用 Skype Online 客戶同盟的必要條件](#prerequisites-for-federating-with-a-skype-for-business-online-customer)。
- 已在內部部署中設定網域存取支援。 這包括建立主機提供者專案，以及設定您的部署以允許來自 商務用 Skype Online 客戶網域的存取。 如需詳細資訊，[請參閱設定 商務用 Skype Online 網域的同盟支援](#configure-federation-support-for-a-skype-for-business-online-domain)。
- 設定您的使用者帳戶以支援同盟。 如需詳細資訊，[請參閱設定使用者存取權以與 商務用 Skype Online 客戶同盟](#configure-user-access-for-federation-with-a-skype-for-business-online-customer)。

在您完成上述所有步驟，且 商務用 Skype Online 客戶的系統管理員完成其線上服務的所有設定以支援與貴組織的同盟之後，請測試組織內部使用者與 商務用 Skype Online 客戶使用者之間的通訊，以驗證通訊。 如果通訊不成功，請使用 Edge Server 中的記錄工具來擷取記錄檔和追蹤檔案，以針對問題進行疑難排解。
