---
title: 設定媒體旁路搭配直接路由
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: article
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: 瞭解如何設定媒體旁路電話系統直接路由Microsoft Teams，方法是一次切換所有使用者，或執行逐步接近 (建議) 。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c0f0ad9d25157058c048b0f12cf72b3755e65e11
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/30/2021
ms.locfileid: "58728682"
---
# <a name="configure-media-bypass-with-direct-routing"></a>設定媒體旁路搭配直接路由

使用直接路由來配置媒體旁路之前，請務必先閱讀使用直接路由 [的媒體旁路方案](direct-routing-plan-media-bypass.md)。

若要開啟媒體旁路，必須符合下列條件：

1.    請確定您的會話邊界控制器 (SBC) 選擇廠商支援媒體旁路，並提供如何在 SBC 上設定旁路的指示。 請參閱認證頁面，以瞭解支援媒體旁路的 SBCs，以及指示。

2.    您需要使用下列命令開啟主幹上的媒體旁路 **：Set-CSOnlinePSTNGateway -Identity <sbc_FQDN> -MediaBypass $true。**

3.    請確定已開啟所需的埠。 


## <a name="migrate-from-non-bypassed-trunks-to-bypass-enabled-trunks"></a>從未忽略的主幹遷移到已啟用旁路的主幹

您可以一次切換所有使用者，也可以按照建議的方式， (逐步) 。

- **一次切換所有使用者。** 如果符合所有條件，您可以開啟旁路模式。 不過，所有生產使用者都會同時切換。 由於您一開始在設定主幹和埠時可能會遇到一些問題，因此您的生產使用者體驗可能會受到影響。 

- **階段方法。 (建議) 。**  使用不同的埠 (為同一個 SBC) 建立新主幹、測試該主幹，並變更使用者指向新主幹的線上語音路由策略。 

  這是建議的方法，因為它可讓轉場更順暢，且使用者體驗不受干擾。 此方法需要 SBC 的組組、新的 FQDN 名稱，以及防火牆的組組。 請注意，您必須確定憑證支援這兩個主幹。 在 SAN 中，您必須有兩個名稱 (sbc1.contoso.com，sbc2.contoso.com) 萬用字元憑證。 

![從未忽略的主幹遷移到已啟用旁路的主幹) 。](media/direct-routing-media-bypass-8.png)

有關如何設定主幹並執行移移的指示，請參閱 SBC 廠商提供的檔：

- [AudioCodes 部署檔](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [Oracle 部署檔](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [功能區通訊部署檔](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [TE-Systems (任何) 部署檔](https://www.anynode.de/anynode-and-microsoft-teams/)

有關已通過直接路由 (SBC 的會話邊界控制) 清單，請參閱通過直接路由認證的 [會話布](direct-routing-border-controllers.md)羅德控制器清單。



## <a name="related-topics"></a>相關主題

[使用直接路由規劃媒體旁路](direct-routing-plan-media-bypass.md)



