---
title: 在商務用 Skype Server 中指派位置原則範圍
ms.reviewer: ''
ms.author: v-mahoffman
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
ms.assetid: e4c66517-c593-4253-b900-7b4dd8bddf2f
description: 規劃商務用 Skype Server 企業語音中的 E9-1-1 部署的位置原則。
ms.openlocfilehash: 2b3733df7e03f9f66b836a889732a023bddb18de
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60770141"
---
# <a name="assign-location-policy-scope-in-skype-for-business-server"></a>在商務用 Skype Server 中指派位置原則範圍
 
規劃商務用 Skype Server 企業語音中的 E9-1-1 部署的位置原則。
  
與其他商務用 Skype Server 原則一樣，位置原則可以指派于多個範圍層級：全域、網站和使用者。 不過，使用者層級位置原則的範圍會與其他商務用 Skype Server 原則的行為稍有不同。 每個使用者的位置原則不僅可以套用至端點物件 (例如使用者和公共區域電話連絡人物件) ，也可以套用到商務用 Skype Server 的網站。 網路網站是與地理位置相關聯之用戶端子網的群組 (但不一定是整個中央網站或分支網站) 中的所有子網。 任何連接至網路網站之子網的用戶端，都會自動挑選指派給該網路網站的位置原則。 在將使用者層級位置原則指派給使用者和網路網站時，網路網站型位置原則會覆寫任何個別使用者原則設定。
  
每個網站都有指派的位置原則，且每個原則都具有指派給它的不同 PSTN 使用方式、通知 URIs 和會議 URIs 值。
  
> [!NOTE]
> 這種特殊原則範圍行為的原因在於，當位於一個 office 網站上的集區的使用者要訪問另一個網站並必須撥打緊急電話時，就會套用適當于該網路網站的 E9-1-1 通話路由設定，不論使用者指派的集區或網站為何。 
  

