---
title: 商務用 Skype Server：主幹間路由
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: '商務用 Skype Server 提供基本的會話管理，其支援主幹間路由。 '
ms.openlocfilehash: dd63f5f03c46e03f313f9cac42a2432499c216b6
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/05/2022
ms.locfileid: "62390995"
---
# <a name="skype-for-business-server-inter-trunk-routing"></a>商務用 Skype Server：主幹間路由

商務用 Skype Server 提供基本的會話管理，其支援主幹間路由。 這項功能可讓商務用 Skype Server 對下游電話語音系統提供呼叫控制功能。 主幹間路由可將 IP-PBX 互連至公用交換電話網路 (PSTN) 閘道，使來自私營分公司 exchange (PBX) phone 的呼叫可以路由傳送至 PSTN，而且傳入 PSTN 通話可以路由傳送至 PBX 電話。 同樣地，商務用 Skype Server 可以相互連接兩個或多個 IP-PBX 系統，讓通話可以在不同 IP-PBX 系統的 PBX 電話之間進行呼叫和接收。 


下圖說明在 PSTN 閘道和 IP-PBX 之間提供 interconnectivity 的商務用 Skype Server。

![PSTN 閘道和 IP-PBX 之間的 Interconnectivity。](../../media/pstn-gateway-ip-pbx.jpg)

下圖說明連接兩個 IP-PBX 系統的商務用 Skype Server。

![連接兩個 PGX 系統的商務用 Skype Server。](../../media/two-ip-pbx-systems.jpg)

