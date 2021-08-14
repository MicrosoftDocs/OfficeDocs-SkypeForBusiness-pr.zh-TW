---
title: Microsoft 365及Office 365 URL 和 IP 位址範圍
ms.reviewer: ''
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 08/21/2018
ms.topic: article
audience: admin
ms.service: msteams
description: 瞭解如何正確設定Microsoft 365或Office 365 URL 和 IP 位址範圍，並盡可能針對與服務Microsoft Teams旁路 Proxy。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingsettings.network.ports
- seo-marvel-mar2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9d0a1270d621c61fc224bbc799f1007ef9818542
ms.sourcegitcommit: 97c2faab08ec9b8fc9967827883308733ec162ea
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/13/2021
ms.locfileid: "58233878"
---
# <a name="microsoft-365-and-office-365-urls-and-ip-address-ranges"></a>Microsoft 365及Office 365 URL 和 IP 位址範圍

請[前往 Microsoft 365](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)和 Office 365 URL 和 IP 位址範圍，以查看必須正確為 Teams 正確配置的 URL、IP 位址、埠和通訊協定的詳細且最新的清單。 Microsoft 會持續改善 Microsoft 365 及 Office 365 服務並加入新的功能，這表示必要的連接埠、URL 和 IP 位址可能會隨著時間變更。 我們建議您透過 [RSS](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) 訂閱，以在更新或變更此資訊時收到通知。

Teams通話和會議體驗建立在新一代雲端式基礎結構上，而新一代雲端式基礎結構也由 Skype 和 商務用 Skype。 這些技術投資包括媒體處理和訊號的 Azure 雲端服務、H.264 視訊編解碼器、SILK 和 Opus 音訊編解碼器、網路復原能力、遙測和品質診斷。 因此，有一些 URL 和 IP 可能需要與 Skype 和 商務用 Skype。

針對所有Microsoft 365或Office 365，建議Teams連接方法會盡可能忽略轉轉 Proxy。 當 Proxy 伺服器位於用戶端Office 365資料中心之間時，媒體可能會強制超過 TCP 而非 UDP，這會影響媒體質量。 下載範例 Proxy PAC 檔案，可用來從管理Microsoft 365端點Office 365[流量。](/office365/enterprise/managing-office-365-endpoints)

如果您的網路和安全性原則需要Microsoft 365或Office 365流量才能在 Proxy 伺服器之間流動，請務必先滿足上述需求，再將Teams部署到生產。 如要詳細資訊，請參閱[適用于](proxy-servers-for-skype-for-business-online.md)Teams 或 商務用 Skype 的 Proxy 伺服器。