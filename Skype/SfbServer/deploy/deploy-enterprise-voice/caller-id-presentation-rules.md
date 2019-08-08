---
title: 在商務用 Skype Server 中建立或修改呼叫者識別碼簡報的翻譯規則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6a643961-a0a1-41d1-96ba-6c428a89d82e
description: '摘要: 瞭解如何使用商務用 Skype Server [控制台] 來設定本機號碼。'
ms.openlocfilehash: ca35b3398732296f435196ffeb38d915472b303d
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233977"
---
# <a name="create-or-modify-a-translation-rule-for-caller-id-presentation-in-skype-for-business-server"></a>在商務用 Skype Server 中建立或修改呼叫者識別碼簡報的翻譯規則

**摘要:** 瞭解如何使用商務用 Skype Server [控制台] 設定本機號碼。

在商務用 Skype Server 中, 呼叫方的電話號碼 (也就是呼叫的電話號碼) 可以從. 164 格式翻譯成_中繼對端_所需的本機撥號格式 (也就是關聯的閘道、私人分支交換 (PBX) 或 SIP 幹線)。 若要這樣做, 您必須先定義一或多個翻譯規則, 才能轉換要求 URI, 然後再將它傳送到幹線對等。

商務用 Skype 伺服器也會提供將呼叫方的電話號碼 (也就是呼叫者撥打的電話號碼) 從 E-164 格式轉換為幹線對等所需的本機撥號格式的選項。 例如, 您可以撰寫翻譯規則, 以從撥號字串開頭移除 + 44, 然後將它取代為0144。

### <a name="to-configure-caller-id-by-using-skype-for-business-server-control-panel"></a>使用商務用 Skype Server [控制台] 設定本機號碼

1. 開啟商務用 Skype Server 的 [控制台]。

2. 在左側導覽列中, 按一下 [**語音路由**], 然後按一下 [**幹線**設定]。

3. 在 [**幹線**設定] 頁面上, 按兩下現有的主幹 (例如 [**全域**幹線]), 以顯示 [**編輯主幹**設定] 對話方塊。

4. 若要設定本機號碼方式:

   - 若要從企業語音部署中所有可用的翻譯規則清單中選擇一或多個規則, 請按一下 [**選取**]。 在 [**呼叫編號翻譯規則**] 中, 按一下您要與主幹建立關聯的規則, 然後按一下 **[確定]**。

   - 若要定義新的翻譯規則, 並將其與骨幹建立關聯, 請按一下 [**新增**]。 如需有關定義新規則的詳細資料, 請參閱在部署檔中[定義翻譯規則](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx)。

   - 若要編輯已經與主幹建立關聯的翻譯規則, 請按一下規則名稱, 然後按一下 [**顯示詳細資料**]。 如需詳細資訊, 請參閱在部署檔中[定義翻譯規則](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx)。

   - 若要複製現有的翻譯規則, 以做為定義新規則的起點, 請按一下規則名稱, 然後按一下 [**複製**], 然後按一下 [**貼**上]。 如需詳細資訊, 請參閱[定義翻譯規則](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx)。

   - 若要從主幹中移除翻譯規則, 請將規則名稱醒目提示, 然後按一下 [**移除**]。

     > [!CAUTION]
     > 如果您已在關聯的中繼對等上設定翻譯規則, 請不要將翻譯規則與幹線建立關聯, 因為這兩個規則可能會衝突。


