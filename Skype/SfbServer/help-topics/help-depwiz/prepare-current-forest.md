---
title: 準備目前的樹系
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.dep.DeployMainForestPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 11f5e359-97eb-45f7-a730-9ddbbaa40b83
description: 若要準備 Active Directory 網域服務林，您必須成功地延伸架構，如執行架構準備的主題中所述，並確定架構已複製。
ms.openlocfilehash: 4286ff0bd9b3291f631e3466b0e790174807a8bf
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2020
ms.locfileid: "41687396"
---
# <a name="prepare-current-forest"></a>準備目前的樹系

若要準備 Active Directory 網域服務林，您必須成功地延伸架構，如執行[架構準備](https://technet.microsoft.com/library/067726ae-fd3f-4133-a32f-26d2603ac674.aspx)的主題中所述，並確定架構已複製。

完成這些先決條件之後，您就可以開始 [步驟 3：準備目前的樹系]****。若要準備樹系，請在樹系根中以 Domain Admins 成員身分 (或是以正在準備之樹系的 Enterprise Admins 成員身分) 登入樹系根裡的電腦。

1. 在「部署精靈」的 [步驟 3：準備目前的樹系] **** 中，按一下 [執行]****。

2. 在 [準備樹系] **** 頁面上，按 [下一步]****。

    > [!NOTE]
    > 您可以在 [林準備] 中，選擇要放置商務用 Skype Server 2015 通用群組的位置。 請選擇和組織需求一致的位置。

3. 在 [執行命令] **** 頁面上，尋找 [工作狀態: 已完成]****，然後按一下 [檢視記錄檔]****。確定沒有任何錯誤。檢閱相關警告，判斷這些是否為基礎結構預期的典型錯誤。

4. 在記錄中的 [**動作**] 欄底下，展開 [**林準備**]，在每個工作的結尾尋找** \<成功\> **執行結果，確認已成功完成 [目錄林準備]，然後關閉記錄，然後按一下 **[完成]**。

5. 在執行網域準備前，請等候 Active Directory 網域服務複製完成，或強制複製到林根網網域控制站的**Active Directory 網站和服務**管理單元中所列的所有網網域控制站。 在所有 Active Directory 網站的網網域控制站之間強制進行複製，以在幾分鐘內進行複製。

    > [!TIP]
    > 如果您需要查看由商務用 Skype Server 部署嚮導所建立的記錄檔，您可以在執行步驟之 Active Directory 網域服務使用者的使用者目錄中，找到已執行部署嚮導的電腦上的日誌檔。 例如，如果使用者是以網域 Contoso.net 的網域管理員身分登入，則記錄檔案位於： C:\Users\Administrator.Contoso\AppData\Local\Temp


