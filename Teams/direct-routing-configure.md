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
description: 瞭解如何設定 Microsoft 直接路由，將您的內部部署電話語音基礎結構連線至 Teams Phone System。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: cf6a180b558edad23450fad3991ee2c646f6cf55
ms.sourcegitcommit: 830357674103c0c5c99bd73d40261afe02a2da49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/09/2022
ms.locfileid: "67291399"
---
# <a name="configure-direct-routing"></a>設定直接路由

直接路由可讓您將內部部署電話語音基礎結構連線至 Microsoft Teams。 本文列出將支援的內部部署會話框線控制器 (SBC) 連線到直接路由所需的高階步驟，以及如何設定 Teams 使用者使用直接路由連線到公用交換電話網 (PSTN) 。 本文連結至相關文章以取得詳細資料。  

如需有關貴組織是否適合使用直接路由的相關資訊，請參閱 [PSTN 連線選項](pstn-connectivity.md)。 如需先決條件和規劃部署的相關資訊，請參閱 [規劃直接路由](direct-routing-plan.md)。

若要完成本文所述的步驟，系統管理員需要熟悉 PowerShell Cmdlet。 如需使用 PowerShell 的詳細資訊，請參閱[為Windows PowerShell設定您的電腦](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)。 

執行這些文章中的步驟之前，Microsoft 建議您確認您的 SBC 已按照 SBC 廠商的建議進行設定： 

- [AudioCodes 部署檔](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [Oracle 部署檔](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [功能區通訊部署檔](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [TE-Systems (任何節點) 部署檔](https://www.anynode.de/anynode-and-microsoft-teams/)
- [元切換部署檔](https://www.metaswitch.com/products/core-network/perimeta-sbc)

如需支援的 SBC 的完整清單，請參閱 [通過直接路由認證的會話框線控制器](direct-routing-border-controllers.md)。

若要設定電話系統並讓使用者使用直接路由，請遵循下列步驟： 

- **步驟 1.** [使用電話系統連接 SBC 並驗證連線](direct-routing-connect-the-sbc.md)
- **步驟 2.** [啟用使用者的直接路由、語音和語音信箱](direct-routing-enable-users.md)
- **步驟 3.** [設定通話路由](direct-routing-voice-routing.md)
- **步驟 4.** [將數位翻譯成替代格式](direct-routing-translate-numbers.md) 

如果您要為多個租使用者設定 SBC，您也會想要閱讀為 [多個租使用者設定 SBC](direct-routing-sbc-multiple-tenants.md)。

## <a name="support-boundaries"></a>支援邊界
與認證裝置一起使用時，Microsoft 僅支援具有直接路由的電話系統。 如果發生問題，您必須先連絡 SBC 廠商的客戶支援。 如有必要，SBC 廠商會透過內部管道將問題呈報給 Microsoft。 Microsoft 保留拒絕非認證裝置透過直接路由連接到電話系統的支援案例的權利。 如果 Microsoft 判斷客戶的直接路由問題與廠商的 SBC 裝置有關，則客戶需要與 SBC 廠商重新聯繫以尋求支援。

## <a name="related-topics"></a>相關主題

[規劃您的語音解決方案](cloud-voice-landing-page.md)

[PSTN 連線選項](pstn-connectivity.md)

[規劃直接路由](direct-routing-plan.md)
