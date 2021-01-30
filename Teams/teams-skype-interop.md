---
title: 團隊與 Skype 互通性
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
description: 瞭解貴組織中的團隊使用者與 Skype (消費者) 使用者之間的互通性功能。
localization_priority: Normal
ms.openlocfilehash: 8bb6a83eddc60ff680d1a08c7266e082dd8b0188
ms.sourcegitcommit: 2639da2c9f903a9a82866be9db2b69a705c54200
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2021
ms.locfileid: "50055645"
---
# <a name="teams-and-skype-interoperability"></a>團隊與 Skype 互通性

本文將提供 Microsoft 團隊與 Skype (消費者) 之間的互通性功能概覽。 瞭解團隊使用者與 Skype 使用者如何透過聊天和通話以及適用的管理控制項進行通訊。

貴組織中的小組使用者可以使用他們的電子郵件地址與撥號給 Skype 使用者，或相反地呼叫 Skype 使用者。

- 團隊使用者可以使用 Skype 使用者搜尋並開始一對一的純文字交談或音訊/視頻通話。
- Skype 使用者可以搜尋並開始與小組使用者進行一對一的單一文字交談或音訊/視頻通話。

您可以在桌上型電腦、web 版和行動裝置 (Android 和 iOS 上使用這些功能，以供團隊和 Skype) 用戶端使用。 為了獲得最佳體驗，我們建議使用 Skype 版本8.58 及更新版本。

> [!NOTE]
> 在 GCC、GCC 高或 DOD 部署或私人雲端環境中，本文中討論的小組和 Skype 交互操作功能無法使用。

## <a name="chat-and-calling-experience"></a>聊天和通話體驗

以下是聊天和通話體驗的概覽。

### <a name="teams-user-starts-a-chat-or-call-with-a-skype-user"></a>團隊使用者與 Skype 使用者開始聊天或通話

團隊使用者可以在新聊天或搜尋列中輸入他們的電子郵件地址，以搜尋 Skype 使用者。  然後，小組使用者可以在搜尋結果中選取 Skype 使用者，以與他們開始聊天或進行通話。

Skype 使用者可以選擇不顯示在搜尋結果中。 在這種情況下，它們不會顯示在團隊和團隊使用者無法找到的搜尋結果中。

### <a name="skype-user-starts-a-chat-or-call-with-a-teams-user"></a>Skype 使用者與團隊使用者開始聊天或通話

Skype 使用者可以使用他們的電子郵件地址，搜尋並開始與團隊使用者交談。 小組使用者會收到通知，告知他們有來自 Skype 使用者的新訊息，而且必須先接受郵件，才能回復。

- 如果團隊使用者選取 [ **接受**]，就會接受該交談，且兩個使用者都可以相互聊天和呼叫對方。
- 如果團隊使用者選取 [ **封鎖**]，就會封鎖交談，隨後就會封鎖該 Skype 使用者的後續訊息和通話。
- 如果小組使用者選取 [ **查看郵件**]，該訊息會顯示在 [小組] 中，協助使用者決定要接受還是封鎖交談。

> [!NOTE]
> 如果您是從商務用 Skype 升級至小組，且您的使用者是 [僅限團隊] 模式，則會將 Skype 使用者的聊天和呼叫傳送給小組。 如果您的使用者處於 [孤島] 模式，聊天和 Skype 使用者的呼叫會傳送到商務用 Skype。

### <a name="teams-user-blocks-or-unblocks-a-skype-user"></a>小組使用者封鎖或解除封鎖 Skype 使用者

在團隊使用者接受或封鎖來自 Skype 使用者的初始交談要求之後，就可以隨時選擇封鎖或解除封鎖該人員。 他們可以在交談中或在小組中的隱私權設定中執行此動作。 Skype 使用者不會知道他們已被封鎖。

已封鎖的 Skype 使用者以及其他人和公開交換的電話網絡 (PSTN) 小組使用者封鎖的電話號碼，會列在使用者的 [小組中的封鎖式連絡人] 清單中。

## <a name="limitations"></a>有限

- 交談為純文字。 這表示沒有任何豐富的格式設定、@mentions、emoji 或其他任何其他適用于 [原生團隊聊天體驗](native-chat-for-external-users.md)的聊天功能。
- [交談] 只是一對一的。 不支援群組聊天。
- 團隊使用者和 Skype 使用者彼此都看不到彼此的目前狀態。
- 不支援使用 Skype ID 或電話號碼搜尋 Skype 使用者。
- Skype 使用者無法撥打設定來電轉接至其他使用者號碼、代理人號碼或公開交換電話網絡的小組使用者， (PSTN) 號碼。  僅支援語音信箱。
- 不支援互通性升級、群組通話及會議。
- 代理人不支援代表小組使用者呼叫 Skype 使用者的功能。
- 不支援使用聊天的螢幕共用。

## <a name="set-whether-teams-users-can-communicate-with-skype-users"></a>設定團隊使用者是否可與 Skype 使用者通訊

作為系統管理員，您可以使用 Microsoft 團隊系統管理中心或 PowerShell 來設定外部存取設定，以控制貴組織中的小組使用者是否可與 Skype 使用者通訊。 根據預設，此功能已針對新的租使用者開啟。 不過，如果您的網域尚未提供下列 DNS SRV 記錄（例如 _sipfederationtls .com），必須由 IT 系統管理員進行設定。  

**服務**： sipfederationtls<br/>
**通訊協定**： TCP<br/>
**優先順序**：100<br/>
**體重**：1<br/>
**埠**：5061<br/>
**目標**： sipfed.online.lync.com

如果您是從商務用 Skype 升級至小組，您在商務用 Skype 系統管理中心所設定的外部通訊設定會遷移至小組。

### <a name="in-the-microsoft-teams-admin-center"></a>在 Microsoft Teams 系統管理中心

在 Microsoft 團隊系統管理中心中，移至 [**全組織設定**  >  **外部存取**]，然後開啟 [**使用者可以與 Skype 使用者通訊**]。 如需如何設定此和其他外部存取設定的逐步指導，請參閱 [管理團隊中的外部存取](https://docs.microsoft.com/microsoftteams/manage-external-access#allow-or-block-domains)。

### <a name="using-powershell"></a>使用 PowerShell

請執行下列動作： 
1. 搭配使用 [CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/set-csexternalaccesspolicy) Cmdlet 與 ```EnablePublicCloudAccess``` 參數，以控制團隊使用者是否可與 Skype 使用者通訊。 設定參數以 ```true``` 允許團隊使用者與 Skype 使用者通訊。 您可以使用 ```EnablePublicCloudAudioVideoAccess``` 參數來啟用/停用音訊/視頻通話。

2. 將 [CsTenantPublicProvider](https://docs.microsoft.com/powershell/module/skype/Set-CsTenantPublicProvider) Cmdlet 與設定的參數搭配使用， ```Provider``` ```"WindowsLive"``` 讓團隊使用者可以與 Skype 使用者通訊。

## <a name="related-topics"></a>相關主題

- [管理團隊中的外部存取](manage-external-access.md)
- [Teams PowerShell 概觀](teams-powershell-overview.md)
