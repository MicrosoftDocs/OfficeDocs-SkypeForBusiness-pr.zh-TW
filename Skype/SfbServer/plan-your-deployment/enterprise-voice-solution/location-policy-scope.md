---
title: 在商務用 Skype Server 中指派位置原則範圍
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: e4c66517-c593-4253-b900-7b4dd8bddf2f
description: 針對商務用 Skype Server Enterprise Voice 中的 E9-1 1 部署規劃位置原則。
ms.openlocfilehash: 3865db146676ed64da9422d2a8731e44451ec6ac
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802753"
---
# <a name="assign-location-policy-scope-in-skype-for-business-server"></a>在商務用 Skype Server 中指派位置原則範圍
 
針對商務用 Skype Server Enterprise Voice 中的 E9-1 1 部署規劃位置原則。
  
與其他商務用 Skype 伺服器原則一樣，位置原則可以在多個範圍層級指派：全域、網站和使用者。 不過，使用者層級位置原則的運作方式比其他商務用 Skype 伺服器原則稍有不同。 您不僅可以將每個使用者的位置原則套用到端點物件（例如使用者和常見的區域電話連絡人物件），也可以將它們套用到商務用 Skype Server 網路網站。 網路網站是與地理位置相關聯的用戶端子網群組（但不一定是整個中央網站或分支網站中的所有子網）。 連接至網路網站中子網的任何用戶端，都會自動挑選指派給該網路網站的位置原則。 在使用者層級位置原則指派給使用者和網路網站的情況下，網路網站的位置原則會覆寫任何每個使用者的原則設定。
  
每個網路網站都有一個指派的位置原則，而每個原則都有不同的 PSTN 用法、通知 Uri 以及指派給它的會議 Uri 值。
  
> [!NOTE]
> 這個特殊原則範圍行為的原因是，當使用者位於某個 office 網站上的某個召集人造訪另一個網站，而且必須撥打電話時，無論該網路網站是哪個池或網站，都不需要使用 E9-1-1 呼叫路由設定ser 指派給您。 
  

