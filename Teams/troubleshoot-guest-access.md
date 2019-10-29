---
title: 針對 Microsoft 團隊中的來賓存取問題進行疑難排解
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
description: 在 Microsoft 團隊中取得來賓存取的疑難排解及修正問題。
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: eefaece55876bc66905716526884fd21303c630e
ms.sourcegitcommit: 09e719ead5c02b3cfa96828841c4905748d192a3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/28/2019
ms.locfileid: "37754359"
---
<a name="troubleshoot-problems-with-guest-access-in-microsoft-teams"></a>針對 Microsoft 團隊中的來賓存取問題進行疑難排解
======================================================

> [!IMPORTANT]
> 您可能需要等候長達24小時，變更才會生效。 


- 若要在小組中查看來賓存取的目前支援問題，請移至[團隊疑難排解](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/)。
- 若要查看我們是否知道您的問題，請查看[Microsoft 團隊的已知問題](Known-issues.md)。
- 來賓是您組織外部的使用者。 如果有人在您的組織內（包括您的員工、現場承包商或現場代理商），就不能將他們新增為來賓。 同樣適用于您的公司。
- 在[團隊藍圖](https://aka.ms/teamsroadmap)中瞭解近期新增或更新的來賓存取功能。
- 在[團隊 UserVoice](https://aka.ms/TeamsUserVoice)中告訴我們您想要的專案。

## <a name="if-your-guests-are-seeing-license-errors"></a>如果您的客人看到授權錯誤

團隊中的來賓存取使用 Azure Active Directory （Azure AD）商務用企業（B2B）和授權模型。 來賓存取權包含在所有 Office 365 商務版 Premium、Office 365 企業版和 Office 365 教育版訂閱中。 不需要額外的 Office 365 授權。

如果您看到授權錯誤，請務必閱讀[Azure Active DIRECTORY B2B 授權指南](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance)，以判斷授權需求，以符合您組織中的來賓存取需求。


- 來賓授權會根據邀請的組織數來計算。 當您計算所需的授權數量時，請考慮這麼做。
- 無論受邀者是來自另一個 Office 365 租使用者，還是正在使用其個人電子郵件地址，都會針對您的組織計算授權。

## <a name="related-topics"></a>相關主題

[團隊中的來賓存取權](guest-access.md)


