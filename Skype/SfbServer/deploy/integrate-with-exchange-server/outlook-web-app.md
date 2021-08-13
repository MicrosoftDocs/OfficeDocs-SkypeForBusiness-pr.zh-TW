---
title: 設定內部部署商務用 Skype Server 和 Outlook Web App 之間的整合
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/7/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 95a20117-2064-43c4-94fe-cac892cadb6f
description: 摘要：整合商務用 Skype Server 和 Outlook Web App。
ms.openlocfilehash: e3bee7a66ec054e316f50ce86839b86d4ecb16ea2333302b12dedb408580c4f1
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54331855"
---
# <a name="configure-integration-between-on-premises-skype-for-business-server-and-outlook-web-app"></a>設定內部部署商務用 Skype Server 和 Outlook Web App 之間的整合

**摘要：** 整合商務用 Skype Server 和 Outlook Web App。

使用內部部署商務用 Skype Server 部署的客戶可以設定混合式部署模式中 Microsoft Exchange Online Microsoft Outlook Web App 的互通性。 互通性功能包括單一登入和立即訊息 (IM) 和目前狀態整合與 Outlook Web App 介面。 若要啟用此整合，您必須完成下列工作，以在內部部署商務用 Skype Server 部署中設定 Edge Server：

- 設定共用 SIP 位址空間

- 在 Edge Server 上設定裝載提供者

- 驗證更新的中央管理存放區複寫

## <a name="configure-a-shared-sip-address-space"></a>設定共用 SIP 位址空間

若要將內部部署商務用 Skype Server 與 Exchange Online 整合，您必須設定共用 SIP 位址空間。 商務用 Skype Server 和 Exchange Online 服務都支援相同的 SIP 網域位址空間。

使用商務用 Skype Server 管理命令介面，使用下列範例所示的參數執行 **Set-CSAccessEdgeConfiguration** 指令程式，以設定同盟的 Edge Server：

```powershell
Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
```

- **AllowFederatedUsers** 參數會指定是否允許內部使用者與來自同盟網域的使用者進行通訊。 此屬性還會決定內部使用者是否可以使用商務用 Skype Server 和 Exchange Online 與共享 SIP 位址空間案例中的使用者進行通訊。

如需使用商務用 Skype Server 管理命令介面的詳細資訊，請參閱[商務用 Skype Server 管理命令](../../manage/management-shell.md)介面。

## <a name="configure-a-hosting-provider-on-the-edge-server"></a>在 Edge Server 上設定裝載提供者

使用商務用 Skype Server 管理命令介面，使用下列範例中的參數執行 **New-CsHostingProvider** Cmdlet，以在 Edge Server 上設定裝載提供者：

```powershell
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

> [!NOTE]
> 如果您使用的是中國在中國運作的 Microsoft 365 或 Office 365，請將此範例中的 ProxyFqdn 參數值取代為由世紀所運作之服務的 FQDN ( "exap.um.outlook.com" ) ： "exap.um.partner.outlook.cn"。 如果您使用 Microsoft 365 或 Office 365 GCC High，請將此範例中的 ProxyFqdn 參數值取代為 ) High： "exap.um.office365.us" 的 FQDN ( "exap.um.outlook.com" GCC。

- **Identity** 為您要 (建立的裝載提供者指定唯一的字串值識別碼，例如，"Exchange Online" ) 。 包含空格的值必須用雙引號括住。

- **Enabled** 會指出網域和裝載提供者之間的網路連線是否已啟用。 這必須設定為 True。

- **EnabledSharedAddressSpace** 指出是否將以共用 SIP 位址空間案例使用裝載提供者。 這必須設定為 True。

- **HostsOCSUsers** 指出裝載提供者是用於主控 Office 通訊伺服器或商務用 Skype Server。 這必須設定為 False。

- **ProxyFQDN** 會指定裝載提供者所使用 Proxy 伺服器的完整網域名稱 (FQDN)。 Exchange Online，FQDN 是 exap.um.outlook.com。

- **IsLocal** 指出裝載提供者所使用的 proxy 伺服器是否包含在您的商務用 Skype Server 拓撲中。 這必須設定為 False。

- **VerificationLevel** 會指出所傳送至及傳送自裝載提供者的郵件所允許的驗證層級。 指定 **UseSourceVerification**，取決於從裝載提供者傳送的郵件中所包含的驗證層級。 若未指定此層級，郵件將被拒絕為無法驗證。

## <a name="verify-replication-of-the-updated-central-management-store"></a>驗證更新的中央管理存放區複寫

您在上述各節中使用 Cmdlet 所做的變更，會自動套用至 Edge Server，通常需要不到一分鐘才能進行複製。 您可以驗證複寫狀態，然後使用下列 Cmdlet，確認是否已將變更套用至 Edge Server。

若要確認複寫更新，請在商務用 Skype Server 部署的內部伺服器上執行下列 Cmdlet：

```powershell
Get-CsManagementStoreReplicationStatus
```
檢查是否所有複本的 UpToDate 值都顯示為 TRUE。

若要確認是否已套用變更，請在 Edge Server 上執行下列 Cmdlet：

```powershell
Get-CsHostingProvider -LocalStore
```
請仔細檢查所顯示的資訊是否符合先前步驟中認可的變更。

## <a name="see-also"></a>另請參閱

[在主控 Exchange UM 上供應商務用 Skype Server 使用者語音信箱](/previous-versions/office/lync-server-2013/lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um)

[商務用 Skype Server 中主控 Exchange 整合通訊整合](/previous-versions/office/lync-server-2013/lync-server-2013-hosted-exchange-unified-messaging-integration)