---
title: Teams Skype互通性
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: vinbel
search.appverid: MET150
description: 瞭解貴組織中Teams使用者與消費者使用者Skype (互通性) 功能。
ms.localizationpriority: medium
ms.openlocfilehash: 77f268ba0e249118572124cad85af95df69d55a4
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58581177"
---
# <a name="teams-and-skype-interoperability"></a>Teams Skype互通性

本文概觀了消費者與消費者Microsoft Teams之間的互通性Skype () 。 瞭解Teams使用者Skype使用者如何透過聊天和通話，以及適用之系統管理控制項來通訊。

Teams中的使用者可以使用Skype與使用者聊天和通話，反之亦然。

- Teams使用者可以搜尋並啟動一對一純文字交談，或與使用者進行音訊/視Skype通話。
- Skype使用者可以搜尋並啟動一對一純文字交談，或與使用者進行音訊/視Teams通話。

這些功能可在桌面、Web 和行動 (Android 和 iOS) 用戶端Teams Skype。 為了獲得最佳體驗，建議您Skype版本 8.58 及更新版本。

> [!NOTE]
> 本文Teams Skype的交互操作功能不適用於 GCC、GCC 高或 DOD 部署，或私人雲端環境中。

## <a name="chat-and-calling-experience"></a>聊天和通話體驗

以下是聊天和通話體驗概觀。

### <a name="teams-user-starts-a-chat-or-call-with-a-skype-user"></a>Teams使用者開始與使用者聊天或Skype通話

Teams使用者可以在新的聊天或搜尋Skype中輸入電子郵件地址，以搜尋使用者。  使用者Teams搜尋結果中選取Skype使用者，開始聊天或通話。

使用者Skype選擇不顯示在搜尋結果中。 在這種情況下，這些使用者不會顯示在搜尋結果中Teams Teams使用者將無法找到他們。

### <a name="skype-user-starts-a-chat-or-call-with-a-teams-user"></a>Skype使用者開始與使用者聊天或Teams通話

Skype使用者可以使用使用者的電子郵件地址，搜尋Teams開始與使用者聊天。 Teams收到通知，告知使用者有來自Skype的新郵件，且必須先接受郵件，才能回復郵件。

- 如果使用者選取 Teams **，即** 表示已接受交談，而且兩個使用者都可以彼此聊天和通話。
- 如果使用者Teams封鎖，交談會封鎖，而來自該使用者的後續訊息Skype通話會封鎖。
- 如果使用者Teams ，郵件會顯示在 Teams中，這可協助使用者決定是否接受或封鎖交談。

> [!NOTE]
> 如果您從 商務用 Skype 升級到 Teams，而您的使用者是使用 Teams Only 模式，Skype 使用者與 Teams 使用者的聊天和通話會傳送到 Teams。 如果您的使用者是群島模式，則來自 Skype 使用者的聊天和Teams會傳送商務用 Skype。

### <a name="teams-user-blocks-or-unblocks-a-skype-user"></a>Teams使用者封鎖或解除封鎖Skype使用者

在Teams使用者接受或封鎖使用者的初始交談Skype，他們可以選擇隨時封鎖或解除封鎖該人員。 他們可以在交談中或在交談中的隱私權設定中Teams。 Skype使用者不會知道他們遭到封鎖。

封鎖Skype使用者，以及其他人和公用交換電話網路絡 (PSTN) Teams 使用者封鎖的電話號碼，會列在 Teams 中使用者封鎖的連絡人清單中。

## <a name="limitations"></a>限制

- 交談為純文字。 這表示沒有豐富的格式、@mentions、表情符號或其他任何其他聊天功能，可在原生聊天Teams[使用](native-chat-for-external-users.md)。
- 交談是一對一。 不支援群組聊天。
- Teams使用者Skype使用者無法看到彼此的目前狀態。
- 不支援Skype使用者使用Skype識別碼或電話號碼來搜尋使用者。
- Skype使用者無法撥打Teams將呼叫轉撥設定為其他使用者的號碼、代理人號碼或公用交換電話網路 (PSTN) 號碼的使用者。  僅支援語音信箱。
- 不支援交互操作升級、群組通話和會議。
- 不支援代理人代表使用者Skype呼叫使用者Teams功能。
- 不支援使用聊天進行螢幕共用。

## <a name="set-whether-teams-users-can-communicate-with-skype-users"></a>設定Teams使用者是否可以與Skype通訊

做為系統管理員，您可以使用 Microsoft Teams系統管理中心或 PowerShell 來設定外部存取設定，以控制Teams使用者是否可以與Skype通訊。 根據預設，此功能會針對新租使用者開啟。 不過，如果網域尚未提供下列 DNS SRV 記錄 ，例如 _sipfederationtls.contoso.com，則 IT 系統管理員必須配置下列 DNS SRV 記錄。  

**服務**：sipfederationtls<br/>
**通訊協定**：TCP<br/>
**優先順序**：100<br/>
**粗** 細：1<br/>
**埠**：5061<br/>
**目標**：sipfed.online.lync.com

如果您從 商務用 Skype 升級到 Teams，您于系統管理中心商務用 Skype設定的外部通訊設定會移Teams。

### <a name="in-the-microsoft-teams-admin-center"></a>在 Microsoft Teams 系統管理中心

在 Microsoft Teams系統管理中心，前往全 **組織** 設定 外部存取，然後開啟 使用者可以與Skype  >  ******通訊**。 若要取得如何設定此及其他外部存取設定之逐步指南，請參閱在 Teams 中[管理外部Teams。](./manage-external-access.md#allow-or-block-domains)

### <a name="using-powershell"></a>使用 PowerShell

請執行下列動作： 
1. 使用[Set-CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy) Cmdlet 與參數一起控制Teams使用者是否Skype ```EnablePublicCloudAccess``` 通訊。 將參數設定 ```true``` 為Teams使用者與Skype通訊。 您可以使用參數 ```EnablePublicCloudAudioVideoAccess``` 來啟用/停用音訊/視音訊通話。

2. 使用[Set-CsTenantPublicProvider Cmdlet](/powershell/module/skype/Set-CsTenantPublicProvider)與參數集，Teams使用者與Skype ```Provider``` ```"WindowsLive"``` 通訊。

## <a name="related-topics"></a>相關主題

- [管理外部存取Teams](manage-external-access.md)
- [Teams PowerShell 概觀](teams-powershell-overview.md)
