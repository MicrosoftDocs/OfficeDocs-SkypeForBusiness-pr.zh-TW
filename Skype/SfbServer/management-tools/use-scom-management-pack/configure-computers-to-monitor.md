---
title: 設定監視的商務用 Skype 伺服器電腦
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b24ea184-4b3e-4277-a244-157afb4b368b
description: 摘要：在商務用 Skype Server 2015 電腦上安裝 Operations Manager 代理程式檔案以進行監控，並將電腦設定為系統中心 proxy。
ms.openlocfilehash: 5279924c29e8dba11882ca7d172c06894a7808b8
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992470"
---
# <a name="configure-the-skype-for-business-server-computers-that-will-be-monitored"></a>設定監視的商務用 Skype 伺服器電腦

**摘要：** 在商務用 Skype Server 2015 電腦上安裝 Operations Manager proxy 檔案以進行監控，並將電腦設定為系統中心 proxy。

您想要監視的每個商務用 Skype Server 2015 電腦，都必須能夠自行向管理伺服器提供其存在性的報告。 若要啟用此程式，您必須在每個要監視的電腦上安裝 Operations Manager 代理檔案。 安裝完代理程式檔案之後，您必須將電腦設定為系統中心 proxy。 在執行這些程式之前，請務必先在這些電腦上安裝並設定商務用 Skype 伺服器。

## <a name="installing-a-certificate-on-a-watcher-node-located-outside-the-perimeter-network"></a>在周邊網路以外的觀察程式節點上安裝憑證
<a name="watcher_node_outside"> </a>

在周邊網路（例如商務用 Skype Server Edge 伺服器）之外，在企業外部（例如外部綜合交易觀察程式節點）或跨 Active Directory 信任邊界的 System Center Operations Manager 代理程式可能需要系統中心作業管理員閘道伺服器的設定。 此伺服器角色可讓沒有與根管理伺服器有信任關係的代理程式，以引發通知。 如需詳細資訊，請參閱[在 Operations Manager 2012 中管理閘道伺服器](https://technet.microsoft.com/en-us/library/hh212823.aspx)。

如果您在其中一個位置部署代理程式，您也必須要求並設定可讓監視者節點傳送警示給 System Center Operations Manager 的憑證。 為了簡化此程式，Operations Manager 小組已建立一組實用程式，讓您在監視者節點電腦上要求並安裝正確類型的憑證。 如需詳細資訊，以及下載這些實用程式，請參閱[使用憑證產生嚮導輕鬆取得未加入網域之代理程式的憑證](https://go.microsoft.com/fwlink/p/?LinkID=267421&amp;amp;clcid=0x409)。

### <a name="installing-the-operation-manager-agent-files"></a>安裝 Operation Manager 代理程式檔

1. 在系統中心設定媒體上，按兩下 **[setup.exe]。**

2. 在 System Center Operation Manager 安裝程式嚮導中，按一下 [**安裝 Operations Manager 代理**程式]，從 [選用安裝] 底下的 [安裝代理程式]

3. 在 System Center 設定向導中，在 [歡迎使用 System Center Operations Manager 安裝程式嚮導] 頁面上，按一下 **[下一步]**。

4. 在 [目的地資料夾] 頁面上，選取將安裝 Operations Manager 代理程式檔案的資料夾，然後按一下 **[下一步]**。

5. 在 [管理群組設定] 頁面上，選取 [**指定管理群組資訊**]，然後按 **[下一步]**。

6. 在 [管理群組設定] 頁面上，于 [**管理群組名稱**] 方塊中輸入 Operations Manager 管理群組的名稱，然後在 [**管理伺服器**] 方塊中輸入 operations manager 伺服器的主機名稱（例如 [atl-scom-001]）。 如果您變更了 Operations Manager 所使用的埠號，請在 [**管理伺服器埠**] 方塊中輸入新的埠號碼。 否則，請將埠保留為預設值5723，然後按 **[下一步]**。

7. 在 [代理動作帳戶] 頁面上，選取 [**本機系統**]，然後按一下 **[下一步]**

8. 在 [Microsoft Update] 頁面上，選取 [**我不想使用 Microsoft Update** ]，然後按 **[下一步]**。

9. 在 [準備安裝] 頁面上，按一下 [**安裝**]。

10. 在 [完成 System Center Operations Manager 安裝程式嚮導] 頁面上，按一下 **[完成]**。

11. 按一下 **[** 結束]。

針對 System Center 2012，您可以按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **System Center Operations manager 2012**]，然後按一下 [ **Operations 2012 Manager 命令**介面]，確認已建立代理程式。 在 Operations Manager Shell 中，輸入下列 Windows PowerShell 命令，然後按 ENTER：
```PowerShell
Get-SCOMAgent
```

系統會顯示所有 Operations Manager 代理程式的清單。
## <a name="configuring-the-skype-for-business-server-computer-to-participate-in-system-center-discovery"></a>將商務用 Skype Server 電腦設定為參與 System Center 探索
<a name="watcher_node_outside"> </a>

若要確保新的商務用 Skype 伺服器代理參與 System Center Operations Manager 的探索程式，您必須在安裝 System Center Operations Manager 主控台的每台電腦上完成下列程式：

1. 按一下 [管理] 索引標籤上的 [**代理程式管理**]。

2. 按一下 [**探索] 嚮導**，並完成要探索的電腦的嚮導。

3. 重新開機健康代理程式服務。 重新開機服務將會強制發現新電腦。 如果您不重新開機服務，系統中心作業管理員可能需要4小時的時間才能探索新電腦。

4. 確認未在 Operations Manager 事件記錄中記錄任何錯誤事件。

5. 成功推送代理程式的電腦將會顯示在 [代理程式管理] 清單下，而手動安裝代理程式的電腦會顯示在 [掛起的管理] 底下，按一下 [電腦名稱稱]，然後按 [核准]。

6. 以滑鼠右鍵按一下電腦的名稱，然後按一下 [**屬性**]。 在 [內容] 對話方塊的 [安全性] 索引標籤上，選取 [**允許此代理程式充當 proxy 並探索其他電腦上的 managed 物件**]，然後按一下 **[確定]**。


