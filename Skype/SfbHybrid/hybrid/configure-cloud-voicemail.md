---
title: 為內部部署使用者設定雲端語音信箱服務
ms.reviewer: ''
ms.author: dstrome
author: dstrome
manager: serdars
ms.date: 2/11/2019
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.collection: ''
description: 針對位於商務用 Skype Server 上之使用者執行雲端式語音信箱的指示。
ms.openlocfilehash: 4f38c181c84edb695fce54d6da805482563cfe01
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58625745"
---
# <a name="configure-cloud-voicemail-service-for-on-premises-users"></a>為內部部署使用者設定雲端語音信箱服務

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]


## <a name="overview"></a>概觀 
本文說明如何為您的商務用 Skype 內部部署使用者設定 Microsoft 雲端語音信箱服務。  

本文假設您已在支援的拓撲中部署商務用 Skype Server，而且您已符合設定混合式連線的必要條件。

如需有關執行雲端語音信箱的優點、規劃考慮和需求的詳細資訊，請參閱[Plan 雲端語音信箱 service](plan-cloud-voicemail.md)。




設定雲端語音信箱包含下列工作：

1.  確定您已符合[Plan 雲端語音信箱 service](plan-cloud-voicemail.md)中所述的必要條件。

2.  確定您已依照 [規劃混合](plan-hybrid-connectivity.md) 式連線和設定 [混合](configure-hybrid-connectivity.md)式連線中所述的方式設定混合式連線能力。 

3.  如本文所述，[將雲端語音信箱設定為前端伺服器上的裝載提供者](#configure-cloud-voicemail-as-the-hosting-provider)。

4.  如本文所述，[設定主控的語音信箱原則](#configure-a-hosted-voicemail-policy)。

5.  依照本文所述[指派主控的語音信箱原則](#assign-a-hosted-voicemail-policy)。

6.  依照本文所述[，為雲端語音信箱啟用使用者](#enable-a-user-for-cloud-voicemail)。


## <a name="configure-cloud-voicemail-as-the-hosting-provider"></a>將雲端語音信箱設定為裝載提供者 

您可以使用具有下列參數的 New-CsHostingProvider Cmdlet，將雲端語音信箱設定為前端伺服器上的裝載提供者：

- **Identity** 為所建立的裝載提供者指定唯一的字串值識別碼;例如，雲端語音信箱。 

- **Enabled** 會指出網域和裝載提供者之間的網路連線是否已啟用。 此參數必須設定為 True。

- **EnabledSharedAddressSpace** 指出是否將以共用 SIP 位址空間案例使用裝載提供者。 此參數必須設定為 True。

- **HostsOCSUsers** 會指出裝載提供者是否是用來主控商務用 Skype Server 帳戶。 此參數必須設為 False。

- **ProxyFQDN** 會指定主機服務提供者所使用之 proxy 伺服器的完整功能變數名稱 (FQDN) ;例如，proxyserver.contoso.com。 如需此資訊，請與您的裝載提供者連絡。 您無法修改此值。 如果主機服務提供者變更其 proxy 伺服器，您將需要刪除該提供者的專案，然後重新建立。

- **IsLocal** 指出裝載提供者所使用的 proxy 伺服器是否包含在您的商務用 Skype Server 拓撲中。 此參數必須設為 False。

例如，在商務用 Skype 管理命令介面中，下列 Cmdlet 會將雲端語音信箱設定為主控提供者：


```PowerShell
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

## <a name="configure-a-hosted-voicemail-policy"></a>設定主控語音信箱原則

為了確保您組織的語音信箱路由傳送至雲端語音信箱服務，您必須為您的組織設定主控語音信箱原則。 在許多情況下，只需要一個主控的語音信箱原則，您也可以修改全域原則，以符合您的所有需求。 如果您的組織需要多個主控的語音信箱原則，您可以使用 cshostedvoicemailpolicy Cmdlet 新增原則。

若要修改全域原則，請在更新您的組織及 TenantID 後，在商務用 Skype Server 管理命令介面中執行下列命令：

```PowerShell
Set-CsHostedVoicemailPolicy -Identity Global -Description "Global Cloud Voicemail Policy" -Destination exap.um.outlook.com -Organization YourDefaultDomain.onmicrosoft.com
```

- **Destination** 指定主控雲端語音信箱服務之 (FQDN) 的完整功能變數名稱。 此值應設定為 **exap.um.outlook.com**。

- **組織** 是指派給您租使用者的預設網域。 您可以讓租使用者管理員登入 office.com，按一下 [系統管理中心] app，然後流覽至左側的 [ **安裝** ]，然後按一下 [ **網域**]，以取得這項資訊。 例如： mytenant.onmicrosoft.com。

    組織名稱也是 Microsoft 365 或 Office 365 中的預設功能變數名稱。

若要確定已成功建立主控語音信箱原則，請執行下列命令：

```PowerShell
Get-CsHostedVoicemailPolicy
```

## <a name="assign-a-hosted-voicemail-policy"></a>指派主控的語音信箱原則

根據預設，全域主控的語音信箱原則會指派給所有使用者。 如果您使用不同的原則，在為使用者啟用主控語音信箱之前，您必須先使用 [授與 CSHostedVoicemailPolicy 指令程式](/powershell/module/skype/grant-cshostedvoicemailpolicy?view=skype-ps) ，授與使用者所需的主控語音信箱原則。

例如，下列命令會將非全域主控語音信箱原則指派給使用者：


```PowerShell
Get-CsUser -Identity "User1" | Grant-CsHostedVoicemailPolicy -PolicyName "Tag:CloudVoiceMailUsers" 
```

## <a name="enable-a-user-for-cloud-voicemail"></a>為使用者啟用雲端語音信箱

若要讓使用者的語音信箱通話路由傳送至雲端語音信箱，您可以搭配使用[Set-CsUser](/powershell/module/skype/set-csuser?view=skype-ps) Cmdlet 搭配 HostedVoiceMail 參數。 

例如，下列命令會為雲端語音信箱啟用使用者帳戶： 

```powershell
Set-CsUser -Identity "User1" -HostedVoiceMail $True
```

此 Cmdlet 會驗證雲端語音信箱原則--位於全域、網站或使用者層級--適用于此使用者。 若未套用原則，指令 Cmdlet 會失敗。  

下一個範例會停用雲端語音信箱的使用者帳戶：

```powershell
Set-CsUser -Identity "User1" -HostedVoiceMail $False
```

此 Cmdlet 會在全域、網站或使用者層級驗證沒有主控語音信箱原則--適用于此使用者。 若原則已套用，指令 Cmdlet 會失敗。

> [!NOTE]
>  使用者必須已啟用 enterprise voice，才能使用 Microsoft 雲端語音信箱服務。