---
title: 設定內部部署商務用 Skype Server 和 Outlook Web App 之間的整合
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/7/2016
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 95a20117-2064-43c4-94fe-cac892cadb6f
description: '摘要: 整合商務用 Skype Server 和 Outlook Web App。'
ms.openlocfilehash: d207e366638b8b6fe163d68b527c9b6d33d7a418
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188128"
---
# <a name="configure-integration-between-on-premises-skype-for-business-server-and-outlook-web-app"></a>設定內部部署商務用 Skype Server 和 Outlook Web App 之間的整合

**摘要:** 整合商務用 Skype Server 和 Outlook Web App。

使用內部部署商務用 Skype 伺服器部署的客戶, 可以使用混合式部署模式, 在 Microsoft Exchange Online 的 microsoft Outlook Web App 中設定互通性。 互通性功能包括單一登入與立即訊息 (IM), 以及與 Outlook Web App 介面的目前狀態整合。 若要啟用此整合, 您必須完成下列工作, 才能在內部部署商務用 Skype Server 部署中設定 Edge 伺服器:

- 設定共用的 SIP 位址空間

- 在 Edge 伺服器上設定主機服務提供者

- 驗證已更新的中央管理存放區的複製

## <a name="configure-a-shared-sip-address-space"></a>設定共用的 SIP 位址空間

若要將內部部署商務用 Skype 伺服器與 Exchange Online 整合, 您必須設定共用的 SIP 位址空間。 商務用 Skype Server 和 Exchange Online 服務都支援相同的 SIP 網域位址空間。

使用商務用 Skype Server Management Shell, 透過執行**CSAccessEdgeConfiguration** Cmdlet 來設定同盟的 Edge 伺服器, 方法是使用下列範例所示的參數:

```
Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
```

- **AllowFederatedUsers**參數指定是否允許內部使用者與來自聯盟網域的使用者進行通訊。 這個屬性也會判斷內部使用者是否可以使用商務用 Skype Server 和 Exchange Online, 在共用的 SIP 位址空間案例中與使用者進行通訊。

如需使用商務用 Skype Server Management 命令介面的詳細資料, 請參閱[商務用 Skype Server 管理命令](../../manage/management-shell.md)介面。

## <a name="configure-a-hosting-provider-on-the-edge-server"></a>在 Edge 伺服器上設定主機服務提供者

使用商務用 Skype Server Management Shell, 透過執行**CsHostingProvider** Cmdlet, 在 Edge 伺服器上設定主機服務提供者, 方法是使用下列範例中的參數:

```
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

> [!NOTE]
> 如果您使用的是中國由世紀運營的 Office 365, 請將此範例 ("exap.um.outlook.com") 中 ProxyFqdn 參數的值, 以由世紀運營的服務 FQDN 取代 ("exap.um.partner.outlook.cn")。 如果您使用的是 Office 365 GCC 高版, 請將此範例 ("exap.um.outlook.com") 中的 ProxyFqdn 參數值取代為 [exap.um.office365.us] 的 FQDN: ""。

- 身分**識別**會為您建立的主機服務提供者指定唯一的字串值識別碼 (例如, 「Exchange Online」)。 包含空格的值必須以雙引號括住。

- **Enabled ** 指出網域與裝載提供者之間的網路連線是否已啟用。 這必須設定為 True。

- **EnabledSharedAddressSpace**表示主機服務提供者是否將用於共用的 SIP 位址空間案例中。 這必須設定為 True。

- **HostsOCSUsers**表示主機服務提供者是用來託管 Office 通訊伺服器或商務用 Skype 伺服器。 必須將它設為 False。

- **ProxyFQDN**指定主機提供者所使用之 proxy 伺服器的完整功能變數名稱 (FQDN)。 針對 Exchange Online, FQDN 是 exap.um.outlook.com。

- **IsLocal**表示主機服務提供者所使用的 proxy 伺服器是否包含在您的商務用 Skype 伺服器拓撲中。 必須將它設為 False。

- **VerificationLevel**表示傳送到託管提供者的訊息所允許的驗證層級。 指定 **UseSourceVerification**，其依賴包含在裝載提供者發出之訊息內的驗證層級。 如果未指定此等級, 郵件將會因無法驗證而遭到拒絕。

## <a name="verify-replication-of-the-updated-central-management-store"></a>驗證已更新的中央管理存放區的複製

您在前面章節中使用 Cmdlet 所做的變更, 會自動套用至 Edge 伺服器, 且通常需要不到一分鐘的時間來複製。 您可以驗證複製狀態, 然後使用下列 Cmdlet 確認已將變更套用至 Edge 伺服器。

若要驗證複製更新, 請在商務用 Skype Server 部署的內部伺服器上, 執行下列 Cmdlet:

```
Get-CsManagementStoreReplicationStatus
```
檢查 UpToDate 值是否針對所有複本顯示 TRUE。

若要確認已套用變更, 請在 Edge 伺服器上執行下列 Cmdlet:

```
Get-CsHostingProvider -LocalStore
```
請仔細檢查所顯示的資訊是否符合先前步驟中所提交的變更。

## <a name="see-also"></a>另請參閱

[供應商務用 Skype Server 使用者在託管 Exchange UM 上的語音信箱](https://technet.microsoft.com/library/306d3fb5-231b-4f0b-b8d8-0d9083b5ed77.aspx)

[商務用 Skype Server 中的託管 Exchange 整合訊息整合](https://technet.microsoft.com/library/f4de0165-da3b-499e-98fc-28ddd0db02d5.aspx)
