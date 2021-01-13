---
title: 準備目前的樹系
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainForestPrep
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 11f5e359-97eb-45f7-a730-9ddbbaa40b83
ROBOTS: NOINDEX, NOFOLLOW
description: 若要準備 Active Directory 網域服務樹系，您必須順利擴充架構（如執行架構準備的主題中所述），並確定架構已複製。
ms.openlocfilehash: 4881cb85134fef81cd741d834f319a76d4028e59
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833823"
---
# <a name="prepare-current-forest"></a>準備目前的樹系

若要準備 Active Directory 網域服務樹系，您必須順利擴充架構（如執行 [架構準備](https://technet.microsoft.com/library/067726ae-fd3f-4133-a32f-26d2603ac674.aspx)的主題中所述），並確定架構已複製。

完成這些先決條件之後，您就可以開始「步驟 3：準備目前的樹系」。若要準備樹系，請在樹系根中以 Domain Admins 成員身分 (或是以正在準備之樹系的 Enterprise Admins 成員身分) 登入樹系根裡的電腦。

1. 在 [部署精靈] 的「步驟 3：準備目前的樹系」中，按一下 [執行]。

2. 在「準備樹系」頁面上，按 [下一步]。

    > [!NOTE]
    > 樹系準備可讓您選擇放置商務用 Skype Server 通用群組的位置。 請選擇和組織需求一致的位置。

3. 在「執行命令」頁面上，尋找 [工作狀態: 已完成]，然後按一下 [檢視記錄檔]。確定沒有任何錯誤。檢閱相關警告，判斷這些是否為基礎結構預期的典型錯誤。

4. 在記錄檔的 [ **動作** ] 欄中，依序展開 [ **樹系準備**]，尋找 **\<Success\>** 執行結果以驗證樹系準備順利完成，關閉記錄檔，然後按一下 **[完成]**。

5. 等候 Active Directory 網域服務複寫完成，或是強制複寫到樹系根域控制 **站之 Active Directory 網站和服務** 嵌入式管理單元中列出的所有網域控制站，然後再執行網域準備作業。 強制在所有 Active Directory 網站的網域控制站之間進行複寫，以在幾分鐘內進行網站的複寫。

    > [!TIP]
    > 如果您需要複查由商務用 Skype Server 部署嚮導所建立的記錄檔，您可以在執行該步驟之 Active Directory 網域服務使用者的 [使用者] 目錄中，找到其上執行「部署」嚮導的電腦。 例如，如果使用者登入網域 Contoso.net 中的網域管理員，則記錄檔位於： C:\Users\Administrator.Contoso\AppData\Local\Temp


