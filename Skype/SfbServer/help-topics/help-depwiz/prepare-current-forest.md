---
title: 準備目前的樹系
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployMainForestPrep
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 11f5e359-97eb-45f7-a730-9ddbbaa40b83
description: 若要準備 Active Directory 網域服務樹系，您必須順利擴充架構（如執行架構準備的主題中所述），並確定架構已複製。
ms.openlocfilehash: 17257199647a0c51a0eabee9ee0b338680f7bcdf
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/05/2022
ms.locfileid: "62388511"
---
# <a name="prepare-current-forest"></a>準備目前的樹系

若要準備 Active Directory 網域服務樹系，您必須順利擴充架構（如執行 [架構準備](/previous-versions/office/lync-server-2013/lync-server-2013-preparing-the-active-directory-schema)的主題中所述），並確定架構已複製。

完成這些先決條件之後，您就可以開始「步驟 3：準備目前的樹系」。若要準備樹系，請在樹系根中以 Domain Admins 成員身分 (或是以正在準備之樹系的 Enterprise Admins 成員身分) 登入樹系根裡的電腦。

1. 在 [部署精靈] 的「步驟 3：準備目前的樹系」中，按一下 [執行]。

2. 在「準備樹系」頁面上，按 [下一步]。

    > [!NOTE]
    > 樹系準備可讓您選擇放置商務用 Skype Server 2015 通用群組的位置。 請選擇和組織需求一致的位置。

3. 在「執行命令」頁面上，尋找 [工作狀態: 已完成]，然後按一下 [檢視記錄檔]。確定沒有任何錯誤。檢閱相關警告，判斷這些是否為基礎結構預期的典型錯誤。

4. 在記錄檔的 [ **動作** ] 欄中，依序展開 [ **樹系準備**]，尋找 **\<Success\>** 執行結果以驗證樹系準備順利完成，關閉記錄檔，然後按一下 **[完成]**。

5. 等候 Active Directory 網域服務複寫完成，或是強制複寫到樹系根域控制 **站之 Active Directory 網站和服務** 嵌入式管理單元中列出的所有網域控制站，然後再執行網域準備作業。 強制在所有 Active Directory 網站的網域控制站之間進行複寫，以在幾分鐘內進行網站的複寫。

    > [!TIP]
    > 如果您需要複查商務用 Skype Server 部署嚮導所建立的記錄檔，您可以在執行該步驟的 Active directory 網域服務使用者的使用者目錄中，找到已執行部署嚮導的電腦上的記錄檔。 例如，如果使用者登入網域 Contoso.net 中的網域管理員，則記錄檔位於： C:\Users\Administrator.Contoso\AppData\Local\Temp