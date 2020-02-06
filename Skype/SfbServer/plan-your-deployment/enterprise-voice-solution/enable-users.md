---
title: 在商務用 Skype Server 中啟用 E9-1-1 的使用者
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
ms.assetid: 3cc64f5b-492e-4c47-9713-3c376f2aad02
description: 在商務用 Skype Server Enterprise Voice 中，E9-1-1 部署的位置原則所需的決定，包括要啟用哪些使用者，以及如何支援漫遊使用者。
ms.openlocfilehash: 717b127a94fbac966476c681cfb7f6e81d91bde9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802953"
---
# <a name="enable-users-for-e9-1-1-in-skype-for-business-server"></a>在商務用 Skype Server 中啟用 E9-1-1 的使用者
 
在商務用 Skype Server Enterprise Voice 中，E9-1-1 部署的位置原則所需的決定，包括要啟用哪些使用者，以及如何支援漫遊使用者。
  
在用戶端註冊期間，商務用 Skype 伺服器會使用位置原則來設定企業語音使用者的 E9 屬性。 此原則包含定義如何執行 E9-1-1 的設定。 例如，位置原則包含緊急撥號字串等資訊，以及如果位置資訊服務不會自動提供某個位置，是否需要使用者手動輸入位置。 如需位置原則的完整定義，請參閱[規劃商務用 Skype Server 的位置原則](location-policies.md)。
  
商務用 Skype 伺服器可將位置原則指派給基於子網的客戶，或是根據全域、每個網站或每個使用者的原則來指派給使用者。 若要協助您決定將如何啟用使用者，您應該先回答下列問題。
  
 **您是否計畫要啟用所有使用者，或限制對企業特定地理區域的支援？**
  
> 您可以使用全域位置原則，將位置指派給企業中的所有使用者。 不過，您可以將位置原則指派給商務用 Skype Server network 網站，然後將子網新增至網站，您可以將 E9-1-1 支援限制在企業內所選的位置，並在每個網站上指定 E9 的路由行為。 
    
 **您是否計畫透過使用者原則啟用個別使用者？**
  
> 如果您想要自訂 E9-1-1 支援，您可以將位置原則直接指派給特定的使用者或常見的區域電話連絡人物件。
    
 **當用戶端在網路外部漫遊或從未定義的子網進行連線時，如果用戶端仍在 E9-1-1，就應該啟用用戶端嗎？**
  
> 如果將使用者指派為全域、網站或每位使用者的位置原則，當用戶端不在已定義的子網中，或位置資訊服務找不到任何位置時，可能需要他們手動在用戶端中輸入位置。 如需詳細資訊，請參閱[定義在商務用 Skype Server 中手動取得位置的使用者體驗](manually-acquiring-a-location.md)。
    

