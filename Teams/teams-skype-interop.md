---
title: Teams與Skype互通性
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
description: 瞭解貴組織中Teams使用者與Skype (消費者) 使用者之間的互通性功能。
ms.localizationpriority: medium
ms.openlocfilehash: dd5bb05f1206baf94f2651899d0c49edbf6fe902
ms.sourcegitcommit: 5bb00d639828c744951a39705fefe81ed6698efe
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/20/2022
ms.locfileid: "66167267"
---
# <a name="teams-and-skype-interoperability"></a>Teams與Skype互通性

本文提供您消費者) Microsoft Teams與Skype (互通性功能的概觀。 瞭解Teams使用者和Skype使用者如何透過聊天和通話，以及適用的系統管理控制來進行通訊。

Teams組織中的使用者可以使用他們的電子郵件地址與Skype使用者聊天及通話。

- Teams使用者可以搜尋並開始一對一文字交談，或與Skype使用者進行音訊/視訊通話。
- Skype使用者可以與Teams使用者進行一對一文字交談或音訊/視訊通話。

這些功能適用于桌上型電腦、網路和行動 (Android和iOS) 用戶端，適用于Teams和Skype。 為獲得最佳體驗，建議您Skype版本 8.58 及更新版本。

> [!NOTE]
> 此文章討論的 Teams 和 Skype 互通功能不適用於 GCC、GCC High 或 DOD 部署，或在私人雲端環境中。

## <a name="chat-and-calling-experience"></a>聊天和通話體驗

以下是聊天和通話體驗的概觀。

### <a name="teams-user-starts-a-chat-or-call-with-a-skype-user"></a>Teams使用者開始與Skype使用者聊天或通話

Teams使用者可以在新聊天或搜尋列中輸入Skype使用者的電子郵件地址，藉此搜尋該使用者。  然後Teams使用者可以在搜尋結果中選取Skype使用者，以開始與他們聊天或通話。

Skype使用者可以選擇不出現在搜尋結果中。 在此情況下，它們不會顯示在Teams的搜尋結果中，Teams使用者也無法找到他們。

### <a name="skype-user-starts-a-chat-or-call-with-a-teams-user"></a>Skype使用者開始與Teams使用者聊天或通話

Skype使用者可以使用電子郵件地址搜尋Teams並開始聊天。 Teams使用者收到來自Skype使用者的新訊息，他們必須先接受郵件才能回復。

- 如果Teams使用者選取 [**接受**]，則會接受交談，而且兩個使用者都可以彼此聊天及通話。
- 如果Teams使用者選取 **[封鎖**]，則會封鎖交談，並封鎖來自該Skype使用者的後續訊息和通話。
- 如果Teams使用者選取 [**檢視訊息**]，訊息會顯示在Teams中，這有助於使用者決定是否要接受或封鎖交談。

> [!NOTE]
> 如果您從 商務用 Skype 升級至 Teams，且您的使用者處於Teams只有模式，則Skype使用者對Teams使用者的聊天和通話會傳送給Teams。 如果您的使用者處於群島模式，Skype使用者對Teams使用者的聊天和通話會傳送給商務用 Skype。

### <a name="teams-user-blocks-or-unblocks-a-skype-user"></a>Teams使用者封鎖或解除封鎖Skype使用者

在Teams使用者接受或封鎖Skype使用者的初始交談要求之後，他們可以選擇隨時封鎖或解除封鎖該人員。 他們可以在交談中或在Teams的隱私權設定中執行此動作。 Skype使用者不會知道他們已被封鎖。

封鎖Skype使用者及其他人員以及公用電話交換 (PSTN) Teams使用者封鎖的電話號碼會列在Teams的使用者封鎖連絡人清單中。

## <a name="limitations"></a>限制

- 交談是文字專用。 這表示在[原生Teams聊天體驗](native-chat-for-external-users.md)中，沒有豐富的格式設定、@mentions、表情圖示或其他任何聊天功能。
- 交談是一對一的。 不支援群組聊天。
- Teams使用者和Skype使用者無法看到彼此的目前狀態。
- 不支援使用Skype識別碼或電話號碼搜尋Skype使用者。
- Skype使用者無法撥打設定來電轉接至其他使用者號碼、代理人號碼或公用交換電話網路 (PSTN) 號碼Teams使用者。  僅支援語音信箱。
- 不支援內部升級、群組通話和會議。
- 不支援代理人代表Teams使用者撥打Skype使用者的功能。
- 不支援與聊天共用螢幕畫面。

## <a name="set-whether-teams-users-can-communicate-with-skype-users"></a>設定Teams使用者是否可以與Skype使用者通訊

身為系統管理員，您可以使用 Microsoft Teams 系統管理中心或 PowerShell 來設定外部存取設定，以控制組織中Teams使用者是否能與Skype使用者通訊。 根據預設，新租使用者會開啟此功能。 不過，如果您的網域尚未提供下列 DNS SRV 記錄，則必須由 IT 管理員 設定下列 DNS SRV 記錄，例如 _sipfederationtls._tcp.contoso.com。  

**服務**：sipfederationtls<br/>
**通訊協定**：TCP<br/>
**優先順序**：100<br/>
**重量**：1<br/>
**埠**：5061<br/>
**目標**：sipfed.online.lync.com

如果您從 商務用 Skype 升級到 Teams，您在系統管理中心設定的外部通訊 商務用 Skype設定會移轉到Teams。

### <a name="in-the-microsoft-teams-admin-center"></a>在 Microsoft Teams 系統管理中心

在Microsoft Teams系統管理中心，移至 **[使用者**  >  **外部存取**]，然後開啟 [**使用者可以與Skype使用者通訊]**。 如需如何設定此和其他外部存取設定的逐步指導方針，請參閱[在 Teams 中管理外部存取](./manage-external-access.md#allow-or-block-domains)。

### <a name="using-powershell"></a>使用 PowerShell

請執行下列動作： 
1. [將 Set-CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy) Cmdlet 與 ```EnablePublicCloudAccess``` 參數搭配使用，以控制Teams使用者是否能與Skype使用者通訊。 將參數設定為 ```true``` 可讓Teams使用者與Skype使用者通訊。 您可以使用參數 ```EnablePublicCloudAudioVideoAccess``` 來啟用/停用音訊/視訊通話。

2. [將 Set-CsTenantPublicProvider](/powershell/module/skype/Set-CsTenantPublicProvider) Cmdlet 與 ```Provider``` 設定 ```"WindowsLive"``` 的參數搭配使用，以便Teams使用者能與Skype使用者通訊。

## <a name="related-topics"></a>相關主題

- [在 Teams 中管理外部存取](manage-external-access.md)
- [Teams PowerShell 概觀](teams-powershell-overview.md)
