---
title: 疑難排解 Teams 用戶端的連線問題
ms.reviewer: ''
ms.author: mikeplum
author: MikePlumleyMSFT
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
ms.openlocfilehash: 8974aa7cf54ab61cb15650b839185daad1b82cc7
ms.sourcegitcommit: ff783fad2fb5d412e864e3af2ceaa8fedcd9da07
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/30/2022
ms.locfileid: "66562162"
---
# <a name="troubleshoot-connectivity-issues-with-the-microsoft-teams-client"></a>針對 Microsoft Teams 用戶端的連線問題進行疑難排解

Microsoft Teams 用戶端所發現的問題大多可以追溯到防火牆或 Proxy 連線。 確認防火牆或 Proxy 中已開啟必要的 URL、IP 位址和連接埠，將會讓不必要的疑難排解工作降到最低。 如需 Microsoft Teams 所需 URL 和 IP 的特定資訊，請參閱[Microsoft 365 和 Office 365 URL 和 IP 位址](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2)支援文章。 下列案例需要在防火牆中開啟特定的 URL 和連接埠。

- 驗證

- Microsoft Teams 用戶端連線

- 共同作業

- 媒體

- 共用服務

- 第三方整合

- 商務用 Skype 互通性

- 商務用 Skype 用戶端互通性

## <a name="when-teams-is-offline-or-in-low-bandwidth-conditions"></a>當 Teams 離線或頻寬不足時

好消息是，即使您離線或在低頻寬條件下執行，Teams 仍會持續執行。 Teams 會將您所有未傳送的訊息儲存 (最多 24 小時) ，並在您恢復連線時傳送。 如果您離線超過 24 小時，Teams 可讓您選擇重新傳送或刪除未傳送的訊息。 我們正在努力將這項功能新增至新的聊天，並且會在可用時更新此檔。

## <a name="related-topics"></a>相關主題

[Teams 疑難排解](/MicrosoftTeams/troubleshoot/teams)