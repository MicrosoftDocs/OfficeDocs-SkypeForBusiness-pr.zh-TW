---
title: Edge Server FQDN 設定展開工具
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.EdgeFqdnsSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9e4e9445-0147-4dd6-84f0-b41de142b332
ROBOTS: NOINDEX, NOFOLLOW
description: 若要編輯或指定 Edge Server 的外部設定，您必須先決定是否要針對會話初始通訊協定使用個別的 IP 位址 (SIP) 存取、Web 會議 Edge service 及 Audio/Video Edge service。
ms.openlocfilehash: 49fddf486877711ebd6ba3b0f20960f475a5268ed9cda81632c3ab21a09b83c7
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54328488"
---
# <a name="edge-server-fqdns-settings-expander"></a>Edge Server FQDN 設定展開工具

若要編輯或指定 Edge server 的 **外部設定**，您必須先決定是否要針對會話初始通訊協定使用個別的 IP 位址 (SIP) 存取、Web 會議 Edge service 及 Audio/Video Edge service。

如果您想要讓每一項使用個別 IP 位址，請選取核取方塊 **[為 Web 會議和 A/V 啟用個別 FQDN 和 IP 位址]**。每個服務必須已建立對應的網域名稱系統 (DNS) 主機 (A) 記錄。

對於每個對外的服務，請指定完整網域名稱 (FQDN) 和關聯的連接埠。例如，在 **[SIP 存取]** 中，您可能使用 sip.contoso.com 和關聯的連接埠 5061。

> [!IMPORTANT]
> 如果您為每個對外的服務選取個別 FQDN，則每個服務必須有關聯的唯一連接埠值。 根據預設，SIP 位於連接埠 5061/TLS、Web Conferencing Edge Service 位於連接埠 444/TLS，A/V Conferencing Edge Service 位於連接埠 443/TLS。 如果您變更其中任何設定，包括使用個別 FQDN 和 IP 位址或埠，您必須更新其他所有依賴初始設定值的服務。

如果您決定讓組織的對外服務使用單一 FQDN 和 IP 位址，請清除 **[為 Web 會議和 A/V 啟用個別 FQDN 和 IP 位址]** 核取方塊。然後您就可以視需要編輯 **[SIP 存取]** 集區 FQDN 和連接埠值。

> [!IMPORTANT]
> 如果您變更其中任何設定，包括使用個別 FQDN 和 IP 位址或埠，您必須更新其他所有依賴初始設定值的服務。

如需定義及設定 Edge service 設定的詳細資訊，請參閱 [定義您的 Edge 拓撲](/previous-versions/office/lync-server-2013/lync-server-2013-define-your-edge-topology)。