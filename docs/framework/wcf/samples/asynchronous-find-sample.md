---
title: 异步查找示例
ms.date: 03/30/2017
ms.assetid: 7a713a25-c1f4-42e1-8c4a-93d64ca45a3b
ms.openlocfilehash: ed900ba3cd1b55f4e35ec0d2b92ef6b7283b498e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33500260"
---
# <a name="asynchronous-find-sample"></a>异步查找示例
此示例演示如何使用客户端应用程序中的异步查找操作。  
  
## <a name="sample-details"></a>示例详细信息  
 此设计模式的优点是以异步方式将作为查找请求的结果而找到的终结点通知客户端。 若要查看其工作原理，请打开 Client.cs 文件。 请注意，<xref:System.ServiceModel.Discovery.DiscoveryClient> 对象已将两个委托附加到它的事件处理程序。 引发 <xref:System.ServiceModel.Discovery.DiscoveryClient.FindCompleted> 事件时调用一个委托，每次引发 <xref:System.ServiceModel.Discovery.DiscoveryClient.FindProgressChanged> 事件时调用另一个委托。 此示例演示如何在应用程序中使用此模式。  
  
> [!NOTE]
>  此示例使用 HTTP 终结点，若要运行此示例，必须添加正确的 URL ACL。 有关详细信息，请参阅[配置 HTTP 和 HTTPS](../../../../docs/framework/wcf/feature-details/configuring-http-and-https.md)。 使用提升的特权执行下面的命令应添加相应的 ACL。 如果该命令无效，则可能需要使用你的域和用户名替换以下自变量。 `netsh http add urlacl url=http://+:8000/ user=%DOMAIN%\%UserName%`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>设置、生成和运行示例  
  
1.  使用 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 打开 AsyncFind.sln。  
  
2.  按 Ctrl+Shift+B 生成解决方案。  
  
3.  打开 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 命令提示，导航到 \WCF\Basic\Discovery\AsyncFind\CS\service\bin\Debug 或 \WCF\Basic\Discovery\AsyncFind\VB\service\bin\Debug 目录，然后运行 Service.exe。  
  
4.  该服务启动后，导航到 \WCF\Basic\Discovery\AsyncFind\CS\client\bin\Debug 或 WCF\Basic\Discovery\AsyncFind\VB\client\bin\Debug 目录，然后运行 Client.exe。  
  
5.  您将看到，客户端能够查找和调用该服务。  
  
> [!IMPORTANT]
>  您的计算机上可能已安装这些示例。 在继续操作之前，请先检查以下（默认）目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和针对.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780)下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。 此示例位于以下目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\AsyncFind`  
  
## <a name="see-also"></a>请参阅
