---
title: 疑難排解用戶端Teams問題
ms.reviewer: ''
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: troubleshooting
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
search.appverid: MET150
f1.keywords:
- NOCSH
description: 針對 Microsoft Teams 用戶端的連線問題進行疑難排解，此問題主要是由防火牆或 Proxy 連線所造成，並了解如何加以修正。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: f9ef787a5e103649c1526fab321cc8a9a088254c
ms.sourcegitcommit: 36bc47b2b9ee0e738fa814c31accacfe816da4a3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/09/2021
ms.locfileid: "52856162"
---
# <a name="troubleshoot-connectivity-issues-with-the-microsoft-teams-client"></a>針對 Microsoft Teams 用戶端的連線問題進行疑難排解

Microsoft Teams 用戶端所發現的問題大多可以追溯到防火牆或 Proxy 連線。 確認防火牆或 Proxy 中已開啟必要的 URL、IP 位址和連接埠，將會讓不必要的疑難排解工作降到最低。 如需特定 URL 和 IP Microsoft Teams，請參閱MICROSOFT 365及Office 365 URL 與[IP 位址](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2)支援文章。 下列案例需要在防火牆中開啟特定的 URL 和連接埠。

- 驗證

- Microsoft Teams 用戶端連線

- 共同作業

- 媒體

- 共用服務

- 第三方整合

- 商務用 Skype 互通性

- 商務用 Skype 用戶端互通性

## <a name="when-teams-is-offline-or-in-low-bandwidth-conditions"></a>當Teams離線或低頻寬條件時

好消息是，即使您Teams或是在低頻寬情況下執行，系統仍持續執行。 Teams會將您所有未傳送的訊息 (現有的聊天) 並一回到線上就傳送。 如果您離線超過 24 小時，Teams可讓您選擇重新接收或刪除未接收的郵件。 我們正在努力將這項功能新加入新聊天中，並將于提供時更新此檔。

## <a name="related-topics"></a>相關主題

[Teams 疑難排解](/MicrosoftTeams/troubleshoot/teams)