---
title: 針對 Microsoft Teams 中的來賓存取問題進行疑難排解
author: LolaJacobsen
ms.author: lolaj
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
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: 72c6db7bdc6ff8b765afdf38bfe910552b45cbf2
ms.sourcegitcommit: 3325fd9de57367e9dd60685d1fef096921441a76
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/01/2020
ms.locfileid: "43997254"
---
<a name="troubleshoot-problems-with-guest-access-in-microsoft-teams"></a>針對 Microsoft Teams 中的來賓存取問題進行疑難排解
======================================================

> [!IMPORTANT]
> 您可能需要等候 24 小時，變更才會生效。 


- 若要查看我們是否知道您的問題，請參閱[貴組織中的支援小組](Known-issues.md)。
- 若要查看 Teams 中的來賓存取的最新支援問題，請移至 [Teams 疑難排解](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/)。
- 來賓是指貴組織外的使用者。 如果某人在組織內 (包括您的員工、現場承包商或現場代理商)，他們就無法新增為來賓。 這同樣適用於您的子公司。
- 瞭解 [Teams 藍圖](https://aka.ms/teamsroadmap)中近期新增或更新的來賓存取功能。
- 在 [Teams UserVoice](https://aka.ms/TeamsUserVoice)中告訴我們您想要的內容。

## <a name="if-your-guests-are-seeing-license-errors"></a>如果您的來賓看到授權錯誤

Teams 中的來賓存取使用 Azure Active Directory (Azure AD) 企業對企業 (B2B) 及其授權模型。 來賓存取隨附於所有 Microsoft 365 商務標準版、Office 365 企業版和 Office 365 教育版訂閱。 您不需要額外的 Office 365 授權。

> [!NOTE]
> 您必須在來賓的家用租使用者上啟用團隊，才能在另一個（資源）租使用者上以來賓身分登入和使用團隊。

如果您看到授權錯誤，請務必閱讀[Azure Active DIRECTORY B2B 授權指南](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance)，以判斷授權需求，以符合您組織中的來賓存取需求。


- 系統會針對邀請的組織計算來賓授權。 當您計算所需的授權數量時，請考慮這一點。
- 無論受邀的來賓是來自另一個 Office 365 組織，還是正在使用其個人電子郵件地址，都會針對您的組織計算授權。

## <a name="support-for-b2b-user-types"></a>B2B 使用者類型的支援
目前，Teams 就如同 [Azure B2B 所定義](https://docs.microsoft.com/azure/active-directory/b2b/user-properties)，只支援狀態 1 和狀態 2 類型的來賓使用者。

## <a name="related-topics"></a>相關主題

[Teams 中的來賓存取](guest-access.md)


