---
title: 設定直接路由
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: 瞭解如何設定 Microsoft Phone 系統 Direct 路由，以將您的內部部署電話結構連線至 Microsoft 團隊。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e1c19bfcd4c220ff6b6c53d8731149eaa8b6b4b1
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031769"
---
# <a name="configure-direct-routing"></a>設定直接路由

Microsoft 手機系統 [直接路由] 可讓您將內部部署的電話結構連線至 Microsoft 團隊。 本文列出連接支援的內部部署會話邊界控制器 (SBC) 直接路由，以及如何將團隊使用者設定為使用直接路由來連線至公用的交換電話網絡 (PSTN) 。 本文將連結至相關的文章，以取得詳細資料。  

如需有關直銷路由是否適合貴組織的相關資訊，請參閱 [手機系統 Direct 路由](direct-routing-landing-page.md)。 如需系統必備及規劃部署的相關資訊，請參閱 [規劃直接路由](direct-routing-plan.md)。

> [!Tip]
> 您也可以觀看下列會話，瞭解直接路由的優點、如何規劃，以及部署方式： [直接在 Microsoft 團隊中傳送路線](https://aka.ms/teams-direct-routing)。

若要完成本文所述的步驟，管理員需要熟悉 PowerShell Cmdlet。 如需有關使用 PowerShell 的詳細資訊，請參閱 [設定您的 Windows PowerShell 電腦](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)。 

在執行這些文章中的步驟之前，Microsoft 建議您確認您的 SBC 已按照您的 SBC 廠商的建議進行設定： 

- [AudioCodes 部署檔](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [Oracle 部署檔](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [功能區通訊部署檔](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [TE-系統 (anynode) 部署檔](https://www.anynode.de/anynode-and-microsoft-teams/)
- [Metaswitch 部署檔](https://www.metaswitch.com/products/core-network/perimeta-sbc)

如需支援的 SBCs 完整清單，請參閱針對 [直接路由認證的會話邊界控制器清單](direct-routing-border-controllers.md)。

若要設定 Microsoft 手機系統並讓使用者使用直接路由，請依照下列步驟進行： 

- **步驟1。** [將 SBC 與 Microsoft Phone 系統連接並驗證連接](direct-routing-connect-the-sbc.md)
- **步驟2。** [允許使用者使用直接路由、語音及語音信箱](direct-routing-enable-users.md)
- **步驟3。** [設定語音路由](direct-routing-voice-routing.md)
- **步驟4。** [將數位轉換成替換格式](direct-routing-translate-numbers.md) 

如果您要為多個租使用者設定 SBC，您也會想要 [為多個](direct-routing-sbc-multiple-tenants.md)租使用者閱讀 [設定 sbc]。


## <a name="related-topics"></a>相關主題

[電話系統直接路由](direct-routing-landing-page.md)

[規劃直接路由](direct-routing-plan.md)

