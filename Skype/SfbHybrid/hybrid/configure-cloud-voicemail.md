---
title: 針對內部部署使用者設定雲端語音信箱服務
ms.reviewer: ''
ms.author: dstrome
author: dstrome
manager: serdars
ms.date: 2/11/2019
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: 針對駐留在商務用 Skype Server 上的使用者實施雲端語音信箱的指示。
ms.openlocfilehash: 99fc250ff4c01a0b51e784c165edb99cbb867b3c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36185467"
---
# <a name="configure-cloud-voicemail-service-for-on-premises-users"></a>針對內部部署使用者設定雲端語音信箱服務

## <a name="overview"></a>概觀 
本文說明如何針對商務用 Skype 內部部署使用者設定 Microsoft 雲端語音信箱服務。  

本文假設您已在支援的拓撲中部署商務用 Skype Server, 且您已滿足設定混合式連線性的先決條件。

如需有關實現雲端語音信箱的優點、規劃考慮及需求的詳細資訊, 請參閱[規劃雲端語音信箱服務](plan-cloud-voicemail.md)。




設定雲端語音信箱涉及下列任務:

1.  請確定您符合[規劃雲端語音信箱服務](plan-cloud-voicemail.md)中所述的先決條件。

2.  請確定您已按照[規劃混合式連線性](plan-hybrid-connectivity.md)和設定[混合式連接](configure-hybrid-connectivity.md)性中所述, 設定混合式連線性。 

3.  在[Edge 伺服器上將雲端語音信箱設定為主機提供者](#configure-cloud-voicemail-as-the-hosting-provider-on-the-edge-server), 如本文所述。

4.  如本文所述[設定託管語音信箱原則](#configure-a-hosted-voicemail-policy)。

5.  如本文所述,[指派主持的語音信箱原則](#assign-a-hosted-voicemail-policy)。

6.  如本文所述[, 啟用雲端語音信箱的使用者](#enable-a-user-for-cloud-voicemail)。


## <a name="configure-cloud-voicemail-as-the-hosting-provider-on-the-edge-server"></a>在邊緣伺服器上將雲端語音信箱設定為主機提供者 

您可以透過使用 CsHostingProvider Cmdlet 與下列參數, 將雲端語音信箱設定為前端伺服器上的託管提供者:

- 身分**識別**會為您建立的主機服務提供者指定唯一的字串值識別碼;例如, 雲端語音信箱。 

- **Enabled ** 指出網域與裝載提供者之間的網路連線是否已啟用。 此參數必須設定為 True。

- **EnabledSharedAddressSpace**表示主機服務提供者是否將用於共用的 SIP 位址空間案例中。 此參數必須設定為 True。

- **HostsOCSUsers**表示主機服務提供者是否是用來主持商務用 Skype Server 帳戶。 此參數必須設為 False。

- **ProxyFQDN**指定主機提供者所使用之 proxy 伺服器的完整功能變數名稱 (FQDN);例如, proxyserver.contoso.com。 請與您的主機提供者聯繫以取得此資訊。 您無法修改此值。 如果主機服務提供者變更其 proxy 伺服器, 您將需要刪除該提供者的專案, 然後重新建立。

- **IsLocal**表示主機服務提供者所使用的 proxy 伺服器是否包含在您的商務用 Skype 伺服器拓撲中。 此參數必須設為 False。

例如, 在商務用 Skype 管理命令介面中, 下列 Cmdlet 會將雲端語音信箱配置為主機提供者:


```
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

## <a name="configure-a-hosted-voicemail-policy"></a>設定託管語音信箱原則

若要確保貴組織的語音信箱已傳送到雲端語音信箱服務, 您必須為貴組織設定託管的語音信箱原則。 在許多情況下, 只需要一個主機語音信箱原則, 您可以修改全域原則來符合您的需求。 如果您的組織需要多個託管的語音信箱原則, 您可以使用 cshostedvoicemailpolicy Cmdlet 新增原則。

若要修改全域原則, 請在更新貴組織和 TenantID 之後, 在商務用 Skype Server management shell 中執行下列命令:

```
Set-CsHostedVoicemailPolicy -Identity Global -Description "Global Cloud Voicemail Policy" -Destination exap.um.outlook.com -Organization YourDefaultDomain.onmicrosoft.com -TenantID “11111111-1111-1111-1111-111111111111”
```

- **Destination**指定託管雲端語音信箱服務的完整功能變數名稱 (FQDN)。 此值應該設定為**exap.um.outlook.com**。

- [**組織**] 是指派給您租使用者的預設網域。 您可以透過將租使用者管理員登入 office.com, 按一下 [系統管理中心] app, 流覽至左側的 [**設定**], 然後按一下 [**網域**] 來取得此資訊。 例如: mytenant.onmicrosoft.com。

    組織名稱也是 Office 365 中的預設功能變數名稱。

- **TenantID**是用來識別您在 Office 365 中的租使用者。 如需詳細資訊, 請參閱[尋找您的 Office 365 租使用者識別碼](https://support.office.com/en-us/article/find-your-office-365-tenant-id-6891b561-a52d-4ade-9f39-b492285e2c9b)。

若要確保已成功建立託管的語音信箱原則, 請執行下列命令:

```
Get-CsHostedVoicemailPolicy
```

## <a name="assign-a-hosted-voicemail-policy"></a>指派託管的語音信箱原則

根據預設, 全域託管的語音信箱原則會指派給所有使用者。 如果您使用不同的原則, 您必須先使用[Grant CSHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/grant-cshostedvoicemailpolicy?view=skype-ps) Cmdlet, 將所需的託管語音信箱原則授與使用者。

例如, 下列命令會將非全域託管的語音信箱原則指派給使用者:


```
Get-CsUser -Identity "User1" | Grant-CsHostedVoicemailPolicy -Identity "Tag:CloudVoiceMailUsers" 
```

## <a name="enable-a-user-for-cloud-voicemail"></a>為使用者啟用雲端語音信箱

若要讓使用者的語音信箱呼叫路由到雲端語音信箱, 您可以使用[move-csuser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) Cmdlet 與 HostedVoiceMail 參數。 

例如, 下列命令可為雲端語音信箱啟用使用者帳戶: 

```Set-CsUser -Identity "User1" -HostedVoiceMail $True```

此 Cmdlet 會驗證雲端語音信箱原則--在全域、網站或使用者層級--適用于此使用者。 如果沒有套用任何原則, 則 Cmdlet 失敗。  

下一個範例會針對雲端語音信箱停用使用者帳戶:

```Set-CsUser -Identity "User1" -HostedVoiceMail $False```

此 Cmdlet 會驗證任何託管的語音信箱原則 (在全域、網站或使用者層級) 適用于此使用者。 如果已套用原則, 則 Cmdlet 會失敗。

> [!NOTE]
>  使用者必須是企業語音功能, 才能使用 Microsoft 雲端語音信箱服務。
