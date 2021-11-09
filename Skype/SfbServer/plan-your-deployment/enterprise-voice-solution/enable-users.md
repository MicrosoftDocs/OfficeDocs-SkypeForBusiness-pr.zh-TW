---
title: 在商務用 Skype Server 中啟用 E9-1-1 的使用者
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
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
ms.assetid: 3cc64f5b-492e-4c47-9713-3c376f2aad02
description: 商務用 Skype Server 企業語音中的 E9-1-1 部署的位置原則所需的決策，包括要啟用的使用者以及如何支援漫遊使用者。
ms.openlocfilehash: 631c74f8ee4d91f1a70f1d2edbfa129602913a6f
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/08/2021
ms.locfileid: "60844136"
---
# <a name="enable-users-for-e9-1-1-in-skype-for-business-server"></a>在商務用 Skype Server 中啟用 E9-1-1 的使用者
 
商務用 Skype Server 企業語音中的 E9-1-1 部署的位置原則所需的決策，包括要啟用的使用者以及如何支援漫遊使用者。
  
在用戶端註冊期間，商務用 Skype Server 會使用位置原則，設定已啟用企業語音之使用者的 E9-1-1 屬性。 此原則包含的設定會定義 E9-1-1 實作方式。 例如，位置原則包含緊急撥號字串等資訊，以及如果位置資訊服務不會自動提供某個位置，是否需要使用者手動輸入位置。 如需完整的位置原則定義，請參閱[規劃商務用 Skype Server 的位置原則](location-policies.md)。
  
商務用 Skype Server 可以將位置原則指派給以子網為基礎的用戶端，或根據全域、每個網站或每位使用者原則指派給使用者。 如需判斷該如何啟用使用者，請先回答下列問題。
  
 **您打算啟用所有使用者，還是打算將支援範圍限定在企業的特定地理區域？**
  
> 您可以使用通用位置原則，將某個位置指派給企業中所有的使用者。 不過，您可以將位置原則指派給商務用 Skype Server 網路網站，然後將子網新增至網站，您可以限制 E9-1-1 對企業內所選位置的支援，並以每個網站為基礎指定 E9-1-1 路由行為。 
    
 **您是否打算透過使用者原則啟用個別使用者？**
  
> 如果您想自訂使用者的 E9-1-1 支援，可以直接指派位置原則給特定使用者或公共區域電話連絡人物件。
    
 **當用戶端漫遊至網路外，或從未定義的子網路連線時，是否仍應啟用用戶端的 E9-1-1？**
  
> 如果使用者被指派全域、網站或個別使用者的位置原則，當用戶端不在已定義的子網內，或位置資訊服務找不到任何位置時，他們就可以要求他們手動將位置輸入用戶端。 如需詳細資訊，請參閱[定義在商務用 Skype Server 中手動取得位置的使用者體驗](manually-acquiring-a-location.md)。
    

