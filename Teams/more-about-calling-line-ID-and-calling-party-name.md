---
title: 深入了解通話線路識別碼和來電方名稱
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: roykuntz, jenstr
ms.topic: article
ms.tgt.pltfrm: cloud
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business Online
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
ms.service: msteams
description: 瞭解通話線路識別碼和通話方名稱。
ms.openlocfilehash: 7baae8ff6ed48919e4ee540890dd31a47ad81c943e5ce8e9db8d934331d0ce75
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54350635"
---
# <a name="more-about-calling-line-id-and-calling-party-name"></a>深入了解通話線路識別碼和來電方名稱

CallerID 包含兩個使用者對向的資訊：

- 電話號碼 (稱為 CLID 或電話線識別碼) 。

- 通話方 (通常稱為 CNAM) 。 

進行通話時，CLID (電話號碼) 會路由至目的地的電信 (也稱為終止電信) 。 通話的 CNAM 資訊可能會或可能不會隨著通話路由，因為此資訊取決於國家/地區如何執行 CNAM (如果完全) 。 CNAM 與通話的傳遞可靠性會因國家/地區及處理電話的電信業者而不同 ，無論是作為仲介者或終止電信業者。 

CLID & CNAM 傳輸是終止電信者的責任。 終止電信公司必須支援 CLID & CNAM 功能，並為這兩個值提供最新記錄。 當原始通話時，Microsoft 會可靠地提供 CLID 值，但這些值一旦通過中間電信業者或終止電信業者時，可能不會保持原狀。 如果中間商或終止電信業者變更、省略或截斷 CLID 值，Microsoft 在修正公用電話網絡中這類問題方面幾乎無追索權。

當中間端或終止電信公司延遲重新更新授權資料庫中的 CNAM 資訊時 ，CNAM 中的不一致可能會造成 ，就像美國的情況一樣。 在還沒有 CNAM 授權資料庫的國家/地區，個別電信業者的做法也會造成 CNAM 資訊在通話中完整無缺的問題。 Microsoft 目前不支援美國外的國家/地區的原始 CNAM 資訊。

## <a name="related-topics"></a>相關主題


