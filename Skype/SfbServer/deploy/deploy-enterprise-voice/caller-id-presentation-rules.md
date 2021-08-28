---
title: 在商務用 Skype Server 中建立或修改來電者識別碼簡報的轉譯規則
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6a643961-a0a1-41d1-96ba-6c428a89d82e
description: 摘要：瞭解如何使用商務用 Skype Server 控制台設定來電者識別碼。
ms.openlocfilehash: 7accfe11c22a8b453ac767c80a0c9269fe638c45
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58605592"
---
# <a name="create-or-modify-a-translation-rule-for-caller-id-presentation-in-skype-for-business-server"></a>在商務用 Skype Server 中建立或修改來電者識別碼簡報的轉譯規則

**摘要：** 瞭解如何使用商務用 Skype Server 控制台設定來電者識別碼。

在商務用 Skype Server 中，被叫方的電話號碼 (也就是說，稱為) 的電話號碼可以從 e.164 格式轉譯成 _主幹對等_ (所需的本機撥號格式，也就是關聯的閘道、專用分支 exchange (PBX) 或 SIP 主幹) 。 若要執行此項作業，您必須定義一或多個轉譯規則，以在將其路由傳送至主幹對等之前轉譯要求 URI。

商務用 Skype Server 也可讓您選擇是否要將呼叫者的電話號碼轉譯 (也就是呼叫者撥打的電話號碼，) 從 e.164 格式到主幹對等項所需的本機撥號格式。 例如，您可撰寫轉譯規則，來將撥號字串開頭的 +44 移除，並以 0144 來取代。

### <a name="to-configure-caller-id-by-using-skype-for-business-server-control-panel"></a>使用商務用 Skype Server 控制台設定來電者識別碼

1. 開啟商務用 Skype Server 控制台]。

2. 在左導覽列中，按一下 **[語音路由]**，然後按一下 **[主幹組態]**。

3. 在 **[主幹組態]** 頁面上，按兩下現有的主幹 (例如 **[通用]** 主幹)，顯示 **[編輯主幹組態]** 對話方塊。

4. 若要設定來電者 ID 呈現方式：

   - 若要從企業語音部署中可用之所有轉譯規則的清單中選擇一個或多個規則，請按一下 [**選取**]。 在 **[來電號碼轉譯規則]** 中，按一下您想要與主幹建立關聯的規則，然後按一下 **[確定]**。

   - 若要定義新的轉譯規則並將其與主幹建立關聯，請按一下 **[新增]**。 如需定義新規則的詳細資訊，請參閱部署檔中的  [定義轉譯規則](/previous-versions/office/lync-server-2013/lync-server-2013-defining-translation-rules) 。

   - 若要編輯已與主幹建立關聯的轉譯規則，按一下規則名稱，然後按一下 **[顯示詳細資料]**。如需詳細資訊，請參閱部署文件中的 [Defining Translation Rules](/previous-versions/office/lync-server-2013/lync-server-2013-defining-translation-rules)。

   - 若要複製現有轉譯規則，以用來作為定義新規則時的起點，請按一下規則名稱，再按一下 **[複製]**，然後按一下 **[貼上]**。如需詳細資訊，＜[Defining Translation Rules](/previous-versions/office/lync-server-2013/lync-server-2013-defining-translation-rules)＞。

   - 若要從主幹移除轉譯規則，請反白顯示該規則名稱並按一下 **[移除]**。

     > [!CAUTION]
     > 如果您已在相關聯的主幹對等上設定轉譯規則，則請勿將轉譯規則與主幹建立關聯，因為兩種規則可能會衝突。