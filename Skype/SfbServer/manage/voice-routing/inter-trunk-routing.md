---
title: 商務用 Skype 伺服器中的中繼站間路由
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: '商務用 Skype 伺服器提供基本的會話管理, 並支援 intertrunk 路由。 '
ms.openlocfilehash: 2c5438f78da78870a5dae8c697d4d30d19a316ce
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187018"
---
# <a name="inter-trunk-routing-in-skype-for-business-server"></a>商務用 Skype 伺服器中的中繼站間路由

商務用 Skype 伺服器提供基本的會話管理, 並支援 intertrunk 路由。 此功能可讓商務用 Skype Server 提供對下游電話系統的呼叫控制功能。 Intertrunk 路由可以將 IP PBX 互連至公用的交換電話網絡 (PSTN) 閘道, 讓來自私人分支 exchange (PBX) 電話的呼叫可以路由到 PSTN, 而且傳入 PSTN 呼叫可以路由到 PBX 電話。 同樣地, 商務用 Skype 伺服器可以相互連接兩個或多個 IP PBX 系統, 以便在不同 IP PBX 系統的 PBX 手機之間進行呼叫和接收。 


下圖說明在 PSTN 閘道與 IP PBX 之間提供 interconnectivity 的商務用 Skype 伺服器。

![PSTN 閘道與 IP PBX 之間的 Interconnectivity](../../media/pstn-gateway-ip-pbx.jpg)

下圖說明連接兩個 IP PBX 系統的商務用 Skype 伺服器。

![連接兩個 IP-PGX 系統的商務用 Skype 伺服器](../../media/two-ip-pbx-systems.jpg)

