---
title: 設定要監視的商務用 Skype Server 電腦
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: b24ea184-4b3e-4277-a244-157afb4b368b
description: 摘要：在商務用 Skype Server 2015 電腦上安裝 Operations Manager 代理程式檔案，以加以監控，並設定電腦成為 System Center proxy。
ms.openlocfilehash: 970214c63869362fdc1d69a1146c69c884466129
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/05/2022
ms.locfileid: "62393715"
---
# <a name="configure-the-skype-for-business-server-computers-to-monitor"></a>設定要監視的商務用 Skype Server 電腦

**總結：** 在商務用 Skype Server 2015 電腦上安裝 Operations Manager 代理程式檔案，以加以監控，並設定電腦成為 System Center proxy。

您要監視的每一部商務用 Skype Server 2015 電腦都必須能夠自我報告其存在於管理伺服器。 若要啟用此程式，您必須在要監視的每一部電腦上安裝 Operations Manager 代理程式檔案。 安裝代理程式檔案之後，您必須將電腦設定為充當 System Center proxy。 在執行這些程式之前，請務必先在這些電腦上安裝及設定商務用 Skype Server。

## <a name="installing-a-certificate-on-a-watcher-node-located-outside-the-perimeter-network"></a>將憑證安裝在位於周邊網路外的監看員節點上
<a name="watcher_node_outside"> </a>

在周邊網路中執行的 Operations Manager 代理程式 System Center (例如商務用 Skype Server Edge Server) ，在企業 (（例如外部綜合交易觀察器節點）以外或跨 Active Directory 信任界限的情況下，可能需要設定) Operations Manager 閘道伺服器。 此伺服器角色可讓代理程式與根管理伺服器之間不具有信任關係，以引發警示。 如需詳細資訊，請參閱 [管理 Operations Manager 中的閘道伺服器 2012](/previous-versions/system-center/system-center-2012-R2/hh212823(v=sc.12))。

如果您在這些位置中的其中一個位置部署代理程式，您也需要要求及設定憑證，以啟用監看員節點，將提醒傳送至 System Center Operations Manager。 為了簡化這個程序，Operations Manager 團隊已建立一套公用程式，讓您要求正確類型的憑證，並安裝於監控程式節點電腦上。 如需詳細資訊，以及若要下載這些公用程式，請參閱 [使用憑證產生嚮導輕鬆取得未加入網域之代理程式的憑證](https://techcommunity.microsoft.com/t5/system-center-blog/obtaining-certificates-for-non-domain-joined-agents-made-easy/ba-p/340467)。

### <a name="installing-the-operation-manager-agent-files"></a>安裝 Operation Manager 代理程式檔案

1. 在 System Center 安裝媒體上，按兩下 [ **Setup.exe**]。

2. 在 [System Center Operations manager 安裝程式] 中，按一下 [**安裝 Operations manager 代理程式**]，從 [選用安裝] 底下的安裝代理程式

3. 在 [System Center 安裝精靈] 的 [歡迎使用 System Center Operations Manager 安裝程式] 頁面上，按 **[下一步]**。

4. 在 [目的地資料夾] 頁面上，選取將安裝 Operations Manager 代理程式檔案的資料夾，然後按 **[下一步]**。

5. 在 [管理群組設定] 頁面上，選取 [ **指定管理群組資訊** ]，然後按 **[下一步]**。

6. 在 [管理群組設定] 頁面上的 [ **管理組名** ] 方塊中，輸入 Operations Manager 管理群組的名稱，然後在 [ **管理伺服器** ] 方塊中輸入 operations manager 伺服器的主機名稱 (例如，atl-ws-01-scom-001) 。 如果您變更了 Operations Manager 所使用的埠號碼，請在 [ **管理伺服器埠** ] 方塊中輸入新的埠號碼。 否則，保留預設值5723的埠，然後按 **[下一步]**。

7. 在 [代理程式動作帳戶] 頁面上選取 [**本機系統**]，然後按 **[下一步]**

8. 在 [Microsoft Update] 頁面上，選取 [ **我不想使用 Microsoft 更新** ]，然後按 **[下一步]**。

9. 在 [準備安裝] 頁面上，按一下 [安裝]。

10. 在 [完成 System Center Operations Manager 安裝程式] 頁面上，按一下 **[完成]**。

11. 按一下 **[結束]**。

針對 System Center 2012，您可以按一下 [**開始**]，按一下 [**所有程式**]，然後按一下 [ **System Center operations manager 2012**]，然後按一下 [ **operations 2012 管理員命令** 介面]，以確認已建立代理程式。 在 Operations Manager 殼層中，輸入下列 Windows PowerShell 命令，然後按 enter：
```PowerShell
Get-SCOMAgent
```

將會顯示所有 Operations Manager 代理程式的清單。
## <a name="configuring-the-skype-for-business-server-computer-to-participate-in-system-center-discovery"></a>設定商務用 Skype Server 電腦參與 System Center 探索
<a name="watcher_node_outside"> </a>

若要確定您的新商務用 Skype Server 代理程式參與 System Center Operations manager 的探索程式，您必須在已安裝 System Center Operations manager 主控台的每一部電腦上完成下列程式：

1. 在 [管理] 索引標籤上，按一下 [ **代理程式管理**]。

2. 按一下 [ **探索] [探索]** ，並完成要探索之電腦的嚮導。

3. 重新開機 Health Agent 服務。 重新開機服務將會強制探索新的電腦。 如果您不重新開機服務，在 System Center Operations Manager 探索新電腦之前，可能需要長達4小時。

4. 確認 Operations Manager 事件記錄中未記錄任何錯誤事件。

5. 成功推入代理程式的電腦會顯示在「代理程式管理」清單下，並以手動方式安裝代理人的電腦顯示在 [擱置的管理] 下，按一下 [電腦名稱稱] 並按 [核准]。

6. 在電腦名稱上按一下滑鼠右鍵，然後按一下 [內容]。 在 [內容] 對話方塊的 [安全性] 索引標籤上，選取 [ **允許此代理程式成為 proxy 並探索其他電腦上的 managed 物件**]，然後按一下 **[確定]**。