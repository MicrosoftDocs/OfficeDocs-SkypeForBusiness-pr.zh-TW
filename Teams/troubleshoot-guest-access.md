---
title: 針對 Microsoft Teams 中的來賓存取問題進行疑難排解
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: corbinm
search.appverid: MET150
description: 取得針對 Microsoft Teams 中的來賓存取問題進行疑難排解並修正問題的說明。
f1.keywords:
- NOCSH
ms.localizationpriority: medium
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5b539116fb5e81156a56c5f73146b92eea898765
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58600928"
---
# <a name="troubleshoot-problems-with-guest-access-in-microsoft-teams"></a>針對 Microsoft Teams 中的來賓存取問題進行疑難排解

- 若要瞭解我們是否知道您的問題，請參閱貴[Teams支援人員。](/MicrosoftTeams/troubleshoot/teams-welcome)
- 若要查看 Teams 中的來賓存取的最新支援問題，請移至 [Teams 疑難排解](/MicrosoftTeams/troubleshoot/)。
- 來賓是貴組織外部人員。 如果某人在組織內 (包括您的員工、現場承包商或現場代理商)，他們就無法新增為來賓。 這同樣適用於您的子公司。
- 瞭解 [Teams 藍圖](https://aka.ms/teamsroadmap)中近期新增或更新的來賓存取功能。
- 在 [Teams UserVoice](https://aka.ms/TeamsUserVoice)中告訴我們您想要的內容。

[!INCLUDE [uservoice-disclaimer-note](includes/uservoice-disclaimer-note.md)]

## <a name="if-your-guests-are-seeing-license-errors"></a>如果您的來賓看到授權錯誤

Teams 中的來賓存取使用 Azure Active Directory (Azure AD) 企業對企業 (B2B) 及其授權模型。 來賓存取隨附於所有 Microsoft 365 商務標準版、Office 365 企業版和 Office 365 教育版訂閱。 您不需要額外的 Microsoft 365 或 Office 365 授權。

> [!NOTE]
> Teams來賓的家用租使用者上啟用此功能，來賓才能在另一個 Teams 資源租使用者上以來賓 (使用) 。

如果您看到授權錯誤，請務必閱讀 [Azure AD 外部](/azure/active-directory/external-identities/external-identities-pricing) 身分標識的帳單模型，以判斷授權需求，以滿足貴組織的來賓存取需求。

- 系統會針對邀請的組織計算來賓授權。 當您計算所需的授權數量時，請考慮這一點。
- 無論受邀來賓來自另一個組織Microsoft 365或使用其個人電子郵件地址，授權會計入貴組織。

## <a name="support-for-b2b-user-types"></a>B2B 使用者類型的支援

目前，Teams 就如同 [Azure B2B 所定義](/azure/active-directory/b2b/user-properties)，只支援狀態 1 和狀態 2 類型的來賓使用者。

## <a name="related-topics"></a>相關主題

[Teams 中的來賓存取](guest-access.md)

[Teams 疑難排解](/MicrosoftTeams/troubleshoot/teams)