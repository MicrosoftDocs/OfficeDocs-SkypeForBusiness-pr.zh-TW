---
title: 在商務用 Skype Server 中部署監控
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 244df419-d0a8-4b1d-aedd-a92114172ab6
description: 摘要：瞭解如何在商務用 Skype Server 中部署監控。
ms.openlocfilehash: cbb5fe0974e1b02ce5be472ba91d01221fb7df82
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60764841"
---
# <a name="deploy-monitoring-in-skype-for-business-server"></a>在商務用 Skype Server 中部署監控

**摘要：** 瞭解如何在商務用 Skype Server 中部署監控。

執行這些工作之前，請參閱[商務用 Skype Server 中的監視計畫](../../plan-your-deployment/monitoring.md)。

您通常會完成下列兩個步驟，以執行拓撲中的監控服務：

1. 在設定新的商務用 Skype Server 集區時，啟用監視。  (在商務用 Skype Server 中，集區依集區啟用或停用。 ) 請注意，您可以啟用集區監控，而不需要實際收集監控資料，而是在本檔的設定詳細通話記錄及經驗品質設定一節中說明的處理常式。

2. 將監控存放區 (也就是監控資料庫) 與新集區建立關聯。請注意，單一監控存放區可與多個集區建立關聯。依據安置在登錄器集區的使用者數目，這表示您不需要為每個集區設定個別的監控資料庫。單一監控存放區即可供多集區使用。

雖然在您建立新集區的同時啟用監視通常會比較容易，但也可能會建立停用監視的新集區。 如果您這麼做，可以在稍後使用拓撲產生器來啟用服務：拓撲產生器有提供一種方法，可為集區啟用或停用監視，或是將集區與不同的監控存放區建立關聯。 請注意，即使不再有監控伺服器角色，仍然需要建立一或多個監視存放區：後端資料庫，用來儲存監控服務所收集的資料。 您可以使用 Microsoft SQL Server 2008 R2、Microsoft SQL Server 2012、Microsoft SQL Server 2014 或 Microsoft SQL Server 2019 來建立這些後端資料庫。

> [!NOTE]
> 如果已啟用集區監控，您可以停用收集監控資料的處理常式，而不需變更拓撲：商務用 Skype Server 提供一種方法，讓您能夠停用 (，然後再重新啟用) 通話詳細資料記錄 (CDR) 或經驗品質 (QoE) 資料收集。 如需詳細資訊，請參閱本文件中的＜設定詳細通話記錄和經驗品質設定＞一節。

在商務用 Skype Server 中監控的另一個重要增強專案是商務用 Skype Server 監控報告現在所支援的事實 IPv6：使用 [IP 位址] 欄位的報告會顯示 IPv4 或 IPv6 位址，取決於： 1) 所使用的 SQL 查詢;和，2) IPv6 位址會儲存在監控資料庫中。

> [!NOTE]
> 確定 SQL Server agent service Startup Type 為 [自動]，且 SQL Server Agent service 執行的是存放監控資料庫的 SQL 實例，因此預設監控 SQL Server 維護工作可以根據 SQL Server Agent Service 的控制，以排程的方式來執行。

這份檔會引導您完成安裝及設定商務用 Skype Server 的監控和監視報告的程式。 文件中提供逐步指示，將可協助您：

- 在拓撲中啟用監視，以及將監控存放區與前端集區建立關聯。

- 安裝 SQL Server Reporting Services 和商務用 Skype Server 監控報告。 監視報告是預先設定的報告，針對儲存在監控資料庫中資訊提供不同的觀點。

- 設定詳細通話記錄 (CDR) 和經驗品質 (QoE) 資料收集。 詳細通話記錄可讓您追蹤商務用 Skype Server 功能（例如 Voice over IP (VoIP) 電話）的使用方式;立即訊息 (IM) ;檔案傳輸;音訊/視頻 (A/V) 會議;和應用程式共用會話。 QoE 計量追蹤在組織中建立的音訊和視訊通話品質，包括遺失的網路封包數量、背景雜訊和「抖動」(封包延遲差異) 量。

- 從監控資料庫手動清除 CDR 及/或 QoE 記錄。

## <a name="deployment-checklist-for-monitoring"></a>監控的部署檢查清單

雖然已在每一部前端伺服器上安裝並啟用監視，但您必須先執行幾個步驟，才能實際收集商務用 Skype Server 的監控資料。 這些步驟如下面的檢查清單所述：

|**階段**|**步驟**|**角色與群組的成員資格**|**文件**|
|:-----|:-----|:-----|:-----|
|**安裝必備硬體和軟體** <br/> |在要作為監控之用的後端資料存放區的電腦上，安裝支援的 Microsoft SQL Server 版本。  <br/> |同時也是本機系統管理員群組成員的網域使用者。  <br/> |[受支援的硬體](/previous-versions/office/lync-server-2013/lync-server-2013-supported-hardware) <br/> [伺服器軟體和基礎結構支援](/previous-versions/office/lync-server-2013/lync-server-2013-server-software-and-infrastructure-support) <br/> |
|**[建立適當的內部拓撲以支援監控]** <br/> |使用商務用 Skype Server 拓撲產生器，將監控資料庫新增至拓撲，然後發佈更新的拓撲。  <br/> |如果要定義拓樸，屬於本機使用者群組成員的使用者。  <br/> 如果要發行拓樸，屬於網域管理員群組和 RTCUniversalServerAdmins 群組成員的使用者。  <br/> |[在商務用 Skype Server 中將監控存放區與前端集區產生關聯](associate-a-monitoring-store.md) <br/> |
|**啟用適當的監控設定** <br/> |啟用詳細通話記錄 (CDR) 和/或經驗品質 (QoE) 在全域及（或）網站範圍內監視。  <br/> |屬於 RTCUniversalServerAdmins 群組成員的使用者，或被指派提供 CsCdrConfiguration 和 CsQoEConfiguration Cmdlet 存取權的 RBAC 角色的使用者。  <br/> |[設定商務用 Skype Server 中的詳細通話記錄及經驗品質設定](call-detail-recording-and-qoe.md) <br/> |

## <a name="enable-monitoring"></a>啟用監視

雖然整合的資料收集代理程式會在每一部前端伺服器上自動安裝及啟用，但這並不意味著您會在完成安裝商務用 Skype Server 之後，自動開始收集監控資料。 相反地，您必須執行下列兩項動作：您必須將前端伺服器/前端集區與監控資料庫產生關聯，而且您必須啟用 (CDR) 和/或經驗品質的詳細通話記錄 (QoE) 在全域範圍和/或網站範圍內監視。

如需將前端伺服器或前端集區與監控資料庫相關聯的逐步指示，請參閱部署指南商務用 Skype Server 中的相關主題：[關聯監控存放區與前端集區的關聯](associate-a-monitoring-store.md)。 在建立這些關聯之後，當您發佈新的商務用 Skype Server 拓撲之後，您仍無法收集監視資料。 這是因為預設會在您安裝商務用 Skype Server 時，停用 CDR 和 QoE 資料收集。

若要開始收集資料，您必須啟用 CDR 及/或 QoE 監視。  (請注意，您不需要同時啟用 CDR 和 QoE 監控;如果您願意，您可以啟用一種監控類型，使另一種類型成為停用狀態。 ) 啟用全域範圍內的 CDR 監控，請從商務用 Skype Server 管理命令介面內執行下列命令：

```powershell
Set-CsCdrConfiguration -Identity "global" -EnableCDR $True
```

或者，您可以從商務用 Skype Server 控制台內啟用 CDR 監控。 從商務用 Skype Server 控制台內，完成下列程式：

1. 按一下 [監視]。

2. 在 [詳細通話記錄] 索引標籤上，按兩下 [全域] 設定。

3. 在 [編輯詳細通話記錄 (CDR) 設定] 窗格中，選取 [啟用 CDR 監視]，然後按一下 [認可]。

若要在全域範圍啟用 QoE 監視，請從商務用 Skype Server 管理命令介面中執行此命令：

```powershell
Set-CsQoEConfiguration -Identity "global" -EnableQoE $True
```

如果您願意，也可以在商務用 Skype Server 控制台中啟用 QoE 監視。 請從控制台，完成下列程序：

1. 按一下 [監視]。

2. 在 [經驗品質資料] 索引標籤上，按兩下 [全域] 設定。

3. 在 [編輯經驗品質 (QoE) 設定] 窗格中，選取 [啟用 QoE 資料監視]，然後按一下 [認可]。

如前所述，上述的範例可啟用全域範圍的監視；也就是說，其可啟用您整個組織的 CDR 和 QoE 監視。 此外，您也可以在網站範圍建立個別的 CDR 和 QoE 組態設定，然後再分別針對每個網站啟用或停用監視。 例如，您可以啟用 Redmond 網站的 CDR 監視，然後停用 Dublin 網站的 CDR 監視。 如需管理監控設定設定的詳細資訊，請參閱部署指南主題設定[商務用 Skype Server 中的詳細通話記錄及經驗品質設定](call-detail-recording-and-qoe.md)。

## <a name="see-also"></a>另請參閱

[規劃商務用 Skype Server 中的監控](../../plan-your-deployment/monitoring.md)