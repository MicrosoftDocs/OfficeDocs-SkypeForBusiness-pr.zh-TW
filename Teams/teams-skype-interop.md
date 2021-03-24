---
title: Teams 和 Skype 互通性
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- m365initiative-externalcollab
ms.reviewer: vinbel
search.appverid: MET150
description: 瞭解貴組織中 Teams 使用者與 Skype 使用者與消費者使用者 (互通性) 功能。
localization_priority: Normal
ms.openlocfilehash: e3203c03043dbcdb04370cf3aa26b435fad4a728
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093953"
---
# <a name="teams-and-skype-interoperability"></a>Teams 和 Skype 互通性

本文提供 Microsoft Teams 與 Skype 與消費者帳戶之間的互通性 (概) 。 瞭解 Teams 使用者和 Skype 使用者如何透過聊天和通話以及適用之系統管理控制項來通訊。

您組織的 Teams 使用者可以使用 Skype 使用者的電子郵件地址與 Skype 使用者聊天和通話，反之亦然。

- Teams 使用者可以搜尋並啟動一對一純文字交談，或與 Skype 使用者進行音訊/視音訊通話。
- Skype 使用者可以搜尋和啟動一對一純文字交談，或與 Teams 使用者進行音訊/視音訊通話。

這些功能可在 Android 和 iOS (Android 和 Skype 的桌面) 行動版用戶端上提供。 為了獲得最佳體驗，我們建議您使用 Skype 版本 8.58 及更新版本。

> [!NOTE]
> 本文中討論的 Teams 和 Skype 交互操作功能不適用於 GCC、GCC High 或 DOD 部署，或私人雲端環境。

## <a name="chat-and-calling-experience"></a>聊天和通話體驗

以下是聊天和通話體驗概觀。

### <a name="teams-user-starts-a-chat-or-call-with-a-skype-user"></a>Teams 使用者開始與 Skype 使用者聊天或通話

Teams 使用者可以在新的聊天或搜尋欄中輸入其電子郵件地址，以搜尋 Skype 使用者。  然後，Teams 使用者可以在搜尋結果中選取 Skype 使用者，開始聊天或通話。

Skype 使用者可能會選擇不顯示在搜尋結果中。 在這種情況下，這些人員不會顯示在 Teams 的搜尋結果中，而 Teams 使用者將無法找到他們。

### <a name="skype-user-starts-a-chat-or-call-with-a-teams-user"></a>Skype 使用者開始與 Teams 使用者聊天或通話

Skype 使用者可以使用 Teams 使用者的電子郵件地址搜尋並開始與 Teams 使用者聊天。 Teams 使用者會收到來自 Skype 使用者的新訊息的通知，且必須先接受該訊息，才能回復。

- 如果 Teams 使用者選取了 **接受**，系統即會接受交談，而且兩個使用者都可以彼此聊天和通話。
- 如果 Teams 使用者選取了封鎖，交談會封鎖，而來自該 Skype 使用者的後續訊息和通話會封鎖。
- 如果 Teams 使用者選取了查看 **郵件**，郵件會顯示在 Teams 中，這可協助使用者決定是否要接受或封鎖交談。

> [!NOTE]
> 如果您從商務用 Skype 升級至 Teams，而您的使用者是使用 Teams 模式，Skype 使用者與 Teams 使用者的聊天和通話會傳送到 Teams。 如果您的使用者是群島模式，Skype 使用者與 Teams 使用者的聊天和通話會傳送到商務用 Skype。

### <a name="teams-user-blocks-or-unblocks-a-skype-user"></a>Teams 使用者封鎖或解除封鎖 Skype 使用者

在 Teams 使用者接受或封鎖 Skype 使用者的初始交談要求之後，他們可以選擇隨時封鎖或解除封鎖該人員。 他們可以在交談中或在 Teams 中的隱私權設定中執行這項操作。 Skype 使用者不會知道他們遭到封鎖。

已封鎖的 Skype 使用者，以及其他人和公用交換電話網路絡 (PSTN) Teams 使用者封鎖的電話號碼，會列在 Teams 中使用者封鎖的連絡人清單中。

## <a name="limitations"></a>限制

- 交談為純文字。 這表示沒有豐富的格式、@mentions、表情符號或其他任何原生 Teams 聊天體驗中可用的聊天 [功能](native-chat-for-external-users.md)。
- 交談是一對一。 不支援群組聊天。
- Teams 使用者和 Skype 使用者無法看到彼此的目前狀態。
- 不支援使用 Skype 識別碼或電話號碼搜尋 Skype 使用者。
- Skype 使用者無法撥打設定呼叫轉撥至其他使用者號碼、代理人號碼或公用交換電話網路 (PSTN) 的 Teams 使用者。  僅支援語音信箱。
- 不支援交互操作升級、群組通話和會議。
- 不支援代理人代表 Teams 使用者打電話給 Skype 使用者的能力。
- 不支援使用聊天進行螢幕共用。

## <a name="set-whether-teams-users-can-communicate-with-skype-users"></a>設定 Teams 使用者是否可以與 Skype 使用者通訊

做為系統管理員，您可以使用 Microsoft Teams 系統管理中心或 PowerShell 來設定外部存取設定，以控制貴組織的 Teams 使用者是否可以與 Skype 使用者通訊。 根據預設，此功能會針對新租使用者開啟。 不過，如果網域尚未提供下列 DNS SRV 記錄 ，例如 _sipfederationtls.contoso.com，則 IT 系統管理員必須配置下列 DNS SRV 記錄。  

**服務**：sipfederationtls<br/>
**通訊協定**：TCP<br/>
**優先順序**：100<br/>
**粗** 細：1<br/>
**埠**：5061<br/>
**目標**：sipfed.online.lync.com

如果您從商務用 Skype 升級至 Teams，您于商務用 Skype 系統管理中心所設定的外部通訊設定會移至 Teams。

### <a name="in-the-microsoft-teams-admin-center"></a>在 Microsoft Teams 系統管理中心

在 Microsoft Teams 系統管理中心，前往 **全組織** 設定外部存取，然後開啟  >  ******使用者可以與 Skype 使用者通訊**。 若要取得如何設定此及其他外部存取設定之逐步指南，請參閱在 Teams 中管理 [外部存取](./manage-external-access.md#allow-or-block-domains)。

### <a name="using-powershell"></a>使用 PowerShell

請執行下列動作： 
1. 使用 [Set-CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy) Cmdlet 與參數一起控制 Teams 使用者是否能與 ```EnablePublicCloudAccess``` Skype 使用者通訊。 將參數設定 ```true``` 為允許 Teams 使用者與 Skype 使用者通訊。 您可以使用參數 ```EnablePublicCloudAudioVideoAccess``` 來啟用/停用音訊/視音訊通話。

2. 使用 [Set-CsTenantPublicProvider Cmdlet](/powershell/module/skype/Set-CsTenantPublicProvider) 與參數集，讓 Teams 使用者可以與 ```Provider``` Skype ```"WindowsLive"``` 使用者通訊。

## <a name="related-topics"></a>相關主題

- [在 Teams 中管理外部存取](manage-external-access.md)
- [Teams PowerShell 概觀](teams-powershell-overview.md)