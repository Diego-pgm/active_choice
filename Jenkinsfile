properties ([
  parameters([
    [$class: 'ChoiceParameter',
        description: 'Select the environment',
        choiceType: 'PT_SINGLE_SELECT',
        name: 'env',
        script: [
            $class: 'GroovyScript',
            fallbackScript: [
                classpath: [],
                sandbox: true,
                script:
                    'return[\'Could not get Env\']'
            ],
            script: [
                classpath: [],
                sandbox: true,
                script:
                    '["Dev","QA","Prod"]'
            ]
        ]
    ],
    [$class: 'CascadeChoiceParameter',
        choiceType: 'PT_MULTI_SELECT',
        description: 'Select the server from the dropdown list',
        name: 'server',
        referencedParameters: 'env',
        script: [
            $class: 'GroovyScript',
            fallbackScript: [
                classpath: [],
                sandbox: true,
                script:
                    'return[\'Could not get environment from env param\']'
            ],
            script: [
                classpath: [],
                sandbox: true;
                script:
                    ''' if (env.equals("Dev")){
                        return["devaaa001", "devaaa002", "devbbb001", "devbbb002", "devccc001", "devccc02"]
                        }
                        else if(env.equals("QA")){
                            return["qaaaa001","qabbb002","qaccc003"]
                        }
                        else if(env.equals("Prod")){
                            return["praaa001","prbbb002","prccc003"]
                        }

                    '''
            ]
        ]
    ]
  ])    
])