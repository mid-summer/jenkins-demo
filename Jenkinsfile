pipeline {
    agent any
    triggers {
        GenericTrigger (
            causeString: 'Triggered by develop',
            genericVariables: [[key: 'ref', value: '$.ref']],
            printContributedVariables: true,
            printPostContent: true,
            regexpFilterExpression: 'refs/heads/' + BRANCH_NAME,
            regexpFilterText: 'refs/heads/feature-1',
            token: 'VXnNT5X/GH8Rs'
        )
    }
    stages {
      stage("测试部署") {
            when {
                branch 'feature-1'
            }
          steps {
                echo 'develop branch'
          }
      }
      stage("生产部署") {
            when {
                branch 'main'
            }
          steps {
                echo 'main branch'
          }
      }
    }
}
