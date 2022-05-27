---
title: Microsoft 365和Office 365 URL 和 IP 位址範圍
ms.reviewer: ''
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 08/21/2018
ms.topic: article
audience: admin
ms.service: msteams
description: 瞭解如何正確設定Microsoft 365或Office 365 URL 和 IP 位址範圍，並盡可能略過轉寄 Proxy 以連線至Microsoft Teams服務。
ms.localizationpriority: medium
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
ms.openlocfilehash: 1ebcf7c6595da3e1774571be4c65a796838115b3
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675715"
---
# <a name="microsoft-365-and-office-365-urls-and-ip-address-ranges"></a>Microsoft 365和Office 365 URL 和 IP 位址範圍

移至[Microsoft 365和Office 365 URL 和 IP 位址範圍](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)，取得必須針對Teams正確設定的 URL、IP 位址、埠和通訊協定的詳細最新詳細清單。 Microsoft 會持續改善 Microsoft 365 及 Office 365 服務並加入新的功能，這表示必要的連接埠、URL 和 IP 位址可能會隨著時間變更。 建議您 [透過 RSS 訂閱](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) ，以便在更新或變更此資訊時收到通知。

Teams通話和會議體驗是建置在下一代雲端基礎結構上，同時由Skype和商務用 Skype使用。 這些技術投資包括 Azure 型雲端服務，用於媒體處理和訊號、H.264 視訊編解碼器、SILK 和 Opus 音訊編解碼器、網路復原、遙測和品質診斷。 因此，必須有與 Skype 和 商務用 Skype 相關聯的 URL 和 IP。

針對所有Microsoft 365和Office 365工作負載，建議的Teams服務連線方法會盡可能略過轉寄 Proxy。 當 Proxy 伺服器位於用戶端和Office 365資料中心之間時，媒體可能會被強制使用 TCP 而非 UDP，這會影響媒體質量。 從管理Microsoft 365[和Office 365端點](/office365/enterprise/managing-office-365-endpoints)下載可用來設定流量的 Proxy PAC 檔案範例。

如果您的網路和安全性原則需要Microsoft 365或Office 365流量才能透過 Proxy 伺服器流經，請確定在將Teams部署到生產之前，已符合上述需求。 如需詳細資訊，請參閱[Teams 或 商務用 Skype Online 的 Proxy Server](proxy-servers-for-skype-for-business-online.md)。