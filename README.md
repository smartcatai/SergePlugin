# NAME

Serge::Sync::Plugin::TranslationService::Smartcat - [Smartcat translation server](http://smartcat.ai/) .po synchronization plugin.

# INSTALLATION

    > cpanm Serge::Sync::Plugin::TranslationService::Smartcat

or

    > cpanm https://github.com/ta2-1/smartcat-serge-sync-plugin/tarball/master

# DESCRIPTION

Serge::Sync::Plugin::TranslationService::Smartcat is a syncronization plugin which allows to build an integration between [Serge](https://serge.io/) (Free, Open Source Solution for Continous Localization) and [Smartcat](http://smartcat.ai/).

# DESCRIPTION OF CONFIG PARAMETERS

    sync
    {
        ts
        {
            plugin                      Smartcat

            data
            {
                /*
                    (STRING) Unique Smartcat project id
                */
                project_id              12345678-1234-1234-1234-123456789012

                /*
                    (STRING) [OPTIONAL] Account Id
                    from https://smartcat.ai/ApiAccess/Credentials

                    Default is read from `smartcat-cli` application config
                */
                token_id                12345678-1234-1234-1234-123456789012

                /*
                    (STRING) [OPTIONAL] API key
                    from https://smartcat.ai/ApiAccess/Credentials

                    Default is read from `smartcat-cli` application config
                */
                token                   1_1234567890123456789012345

                # push-ts parameters
                push {
                    /*
                        (STRING) [OPTIONAL]
                        Default is Serge.io PO
                    */
                    disassemble_algorithm_name       Serge.io PO
                }

                # pull-ts parameters
                pull {
                    /*
                        (BOOLEAN) [OPTIONAL] If 'complete_projects'
                        is set to a true value, the whole project will not
                        be pulled from Smartcat if its status doesn't
                        equal 'complete'
                        Default is NO
                    */
                    complete_projects                NO

                    /*
                        (BOOLEAN) [OPTIONAL] If 'complete_documents'
                        is set to a true value, the document will not be
                        pulled from Smartcat if its status doesn't
                        equal 'complete'
                        Default is NO
                    */
                    complete_documents               NO
                }

                /*
                    (STRING) [OPTIONAL]
                    Default is read from `smartcat-cli` application config
                */
                log_file                             /path/to/log/file

                /*
                    (STRING) [OPTIONAL]
                    Default is ".po"
                */
                filetype                             .po

                /*
                    (BOOLEAN) [OPTIONAL] If 'language_file_tree' is set
                    to a true value (EXPERIMENTAL MODE), same '.po' files from
                    direfferent language directories will be added to Smartcat as
                    leafs of the only tree document
                    Default is NO
                */
                language_file_tree                   NO

                /*
                    (BOOLEAN) [OPTIONAL]
                    Default is NO
                */
                debug                                YES
            }
        }

        # other sync parameters
        # ...
    }

# MINIMAL CONFIG SAMPLE

    sync
    {
        ts
        {
            plugin                      Smartcat

            data
            {
                # token and token_id should be set via 'smartcat-cli' config file

                project_id              12345678-1234-1234-1234-123456789012
            }
        }
    }

# AUTHOR

Taras Semenenko <taras.semenenko@gmail.com>
