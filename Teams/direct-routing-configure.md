---
title: 設定直接路由
ms.reviewer: filippse
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
- m365solution-voice
- m365solution-scenario
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: 瞭解如何設定 Microsoft Direct Routing，將您的內部部署電話基礎結構連接到Teams 電話系統。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b72a51008e2a5d55b57809ab5e8ae989f4ed3ec7
ms.sourcegitcommit: 5e9b50cd1b513f06734be6c024ac06d293b27089
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/10/2022
ms.locfileid: "62518575"
---
# <a name="configure-direct-routing"></a>設定直接路由

直接路由可讓您將內部部署電話基礎結構連接到Microsoft Teams。 本文列出將支援的內部部署會話邊界控制器 (SBC) 連接到直接路由所需的高層級步驟，以及如何將 Teams 使用者設定為使用直接路由來連接到公用交換式電話網絡 (PSTN) 。 本文連結至相關文章以尋找詳細資料。  

有關直接路由是否適合貴組織的解決方案，請參閱 [PSTN 連接選項](pstn-connectivity.md)。 有關先決條件和規劃部署的資訊，請參閱 [規劃直接路由](direct-routing-plan.md)。

若要完成本文說明的步驟，系統管理員需要熟悉 PowerShell Cmdlet。 有關使用 PowerShell 的資訊，請參閱設定您的電腦[Windows PowerShell](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)。 

在執行這些文章中的步驟之前，Microsoft 建議您確認 SBC 已按照 SBC 廠商的建議進行配置： 

- [AudioCodes 部署檔](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [Oracle 部署檔](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [功能區通訊部署檔](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [TE-Systems (任何) 部署檔](https://www.anynode.de/anynode-and-microsoft-teams/)
- [Metaswitch 部署檔](https://www.metaswitch.com/products/core-network/perimeta-sbc)

有關支援 SBC 的完整清單，請參閱 [通過直接路由認證的會話邊界控制器](direct-routing-border-controllers.md)。

若要設定電話系統並讓使用者使用直接路由，請遵循下列步驟： 

- **步驟 1。** [連線 SBC 電話系統並驗證連接](direct-routing-connect-the-sbc.md)
- **步驟 2.** [啟用使用者進行直接路由、語音和語音信箱](direct-routing-enable-users.md)
- **步驟 3.** [設定通話路由](direct-routing-voice-routing.md)
- **步驟 4.** [將數位轉換成替代格式](direct-routing-translate-numbers.md) 

如果您要為多個租使用者設定 SBC，您也會想要閱讀為多個租使用者設定 [SBC](direct-routing-sbc-multiple-tenants.md)。


## <a name="related-topics"></a>相關主題

[規劃語音解決方案](cloud-voice-landing-page.md)

[PSTN 連接選項](pstn-connectivity.md)

[規劃直接路由](direct-routing-plan.md)