---
title: 關於商務用 Skype Server 中的主幹間路由
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f687a548-1f2e-48ed-9745-a13dc1f3698f
description: 瞭解商務用 Skype Server 企業語音如何支援主幹間路由。
ms.openlocfilehash: 5a44f9e269985312e31d827254dd7bbfae10bcfd
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/30/2021
ms.locfileid: "58731812"
---
# <a name="about-inter-trunk-routing-in-skype-for-business-server"></a>關於商務用 Skype Server 中的主幹間路由
 
瞭解商務用 Skype Server 企業語音如何支援主幹間路由。
  
商務用 Skype Server 提供基本的會話管理，其支援主幹間路由。 這可讓商務用 Skype Server 對下游電話語音系統提供呼叫控制功能。 主幹間路由可將 IP-PBX 互連至公用交換電話網路 (PSTN) 閘道，使來自私營分公司 exchange (PBX) phone 的呼叫可以路由傳送至 PSTN，而且傳入 PSTN 通話可以路由傳送至 PBX 電話。 同樣地，商務用 Skype Server 可以相互連接兩個或多個 IP-PBX 系統，讓通話可以在不同 IP-PBX 系統的 PBX 電話之間進行呼叫和接收。 
  
下圖說明在 PSTN 閘道和 IP-PBX 之間提供 interconnectivity 的商務用 Skype Server。
  
![連接 PSTN 閘道/IP-PBX 圖表的 Lync Server。](../../media/inter_trunk01.jpg)
  
下圖說明連接兩個 IP-PBX 系統的商務用 Skype Server。
  
![Lync Server 互連 IP-PAX 系統圖表。](../../media/inter_trunk02.jpg)
  

